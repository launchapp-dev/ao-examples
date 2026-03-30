# AO Examples — Autopilot Factory

This repo is an autonomous factory that generates AO workflow example repositories across verticals.
It runs fully on autopilot — an Opus conductor manages the entire operation, including building custom MCP servers when needed.

---

## AO CLI Reference

### Key Commands

```bash
# Daemon
ao daemon start --autonomous       # Start fully autonomous daemon
ao daemon stop                     # Stop daemon
ao daemon status                   # Check if running
ao daemon stream --pretty          # Watch live logs
ao daemon config --pool-size 4     # Set max concurrent agents

# Queue (use this to dispatch work)
ao queue enqueue --title "<name>" --description "<desc>" --workflow-ref <workflow-id>
ao queue list                      # See queued dispatches
ao queue stats                     # Queue statistics
ao queue drop <id>                 # Remove from queue

# Tasks
ao task list                       # List all tasks
ao task get <id>                   # Task details
ao task create "<title>"           # Create task (prefer queue enqueue)

# Workflows
ao workflow list                   # List defined workflows
ao workflow run <id>               # Run a workflow
ao workflow get <id>               # Workflow details
ao workflow cancel <id>            # Cancel running workflow

# Status
ao status                          # Project dashboard
ao now                             # Current focus / inbox
ao errors list                     # Check for errors
```

### Workflow YAML Schema

All workflow config lives in `.ao/workflows/` and is merged together.

#### agents.yaml
```yaml
agents:
  <agent-id>:
    description: "What this agent does"
    system_prompt: |
      Detailed instructions for the agent...
    model: claude-sonnet-4-6          # Model to use
    tool: claude                       # Tool runtime
    mcp_servers:                       # MCP servers this agent can access
      - filesystem
      - github
```

Valid models: `claude-opus-4-6`, `claude-sonnet-4-6`, `claude-haiku-4-5`, `kimi-code/kimi-for-coding`, `minimax/MiniMax-M2.7`, `gemini/gemini-2.5-flash`

#### phases.yaml
```yaml
phases:
  <phase-id>:
    mode: agent                        # agent | command | manual
    agent: <agent-id>                  # Which agent runs this phase
    directive: |
      Specific instructions for this phase...
    capabilities:
      mutates_state: true
      writes_files: true
      requires_commit: true
    # For decision phases:
    decision_contract:
      required_fields: [verdict, reasoning]
    # For command phases:
    command:
      program: bash
      args: ["-c", "echo hello {{subject_title}}"]
      cwd_mode: project_root          # project_root | task_root
      timeout_secs: 300
```

#### workflows.yaml
```yaml
default_workflow_ref: <workflow-id>

workflows:
  - id: <workflow-id>
    name: "Human Name"
    description: "What this workflow does"
    phases:
      - phase-one
      - phase-two
      - phase-three:
          on_verdict:
            rework:
              target: phase-two        # Go back on rework
            fail:
              target: phase-one        # Start over on fail
          max_rework_attempts: 3
    post_success:
      merge:
        strategy: squash
        target_branch: main
        create_pr: true
        auto_merge: true
        cleanup_worktree: true
```

**Important:** `on_verdict` advance is implicit (goes to next phase). Don't use empty string targets.

#### schedules.yaml
```yaml
schedules:
  - id: <schedule-id>
    cron: "*/30 * * * *"               # Standard 5-field cron
    workflow_ref: <workflow-id>
    enabled: true
```

#### mcp-servers.yaml
```yaml
mcp_servers:
  <server-name>:
    command: npx
    args: ["-y", "@modelcontextprotocol/server-filesystem", "/path"]
    env:
      API_KEY: "${API_KEY}"            # Environment variable interpolation
```

### Template Variables in Command Phases

Command phase `args` and `env` values support `{{variable}}` expansion:

| Variable | Value |
|---|---|
| `{{subject_title}}` | Task title (e.g. "blog-generator") |
| `{{subject_id}}` | Task ID (e.g. "TASK-001") |
| `{{subject_description}}` | Task description |
| `{{project_root}}` | Project root path |
| `{{execution_cwd}}` | Current working directory for this execution |
| `{{workflow_id}}` | Workflow instance ID |
| `{{workflow_ref}}` | Workflow definition ID |
| `{{phase_id}}` | Current phase ID |
| `{{dispatch_input}}` | Input JSON from queue enqueue |
| `{{schedule_input}}` | Input from schedule trigger |

**Important:** Do NOT use `${AO_TASK_TITLE}` — these are not environment variables.
Use `{{subject_title}}` in command args instead.

### Rules
- Every agent referenced in phases must exist in agents.yaml
- Every phase referenced in workflows must exist in phases.yaml
- Every MCP server referenced in agents must be declared in mcp-servers.yaml
- `on_verdict` targets must reference valid phase IDs (no empty strings)
- Model names must be exact (see valid models above)

---

## MCP Server Development Reference

### Building a Custom MCP Server (TypeScript)

```typescript
import { Server } from "@modelcontextprotocol/sdk/server/index.js";
import { StdioServerTransport } from "@modelcontextprotocol/sdk/server/stdio.js";
import {
  CallToolRequestSchema,
  ListToolsRequestSchema,
} from "@modelcontextprotocol/sdk/types.js";

const server = new Server(
  { name: "my-mcp-server", version: "1.0.0" },
  { capabilities: { tools: {} } }
);

// Define available tools
server.setRequestHandler(ListToolsRequestSchema, async () => ({
  tools: [
    {
      name: "my_tool",
      description: "What this tool does",
      inputSchema: {
        type: "object",
        properties: {
          param1: { type: "string", description: "Description" },
        },
        required: ["param1"],
      },
    },
  ],
}));

// Handle tool calls
server.setRequestHandler(CallToolRequestSchema, async (request) => {
  const { name, arguments: args } = request.params;
  switch (name) {
    case "my_tool": {
      const result = await callRealAPI(args.param1);
      return { content: [{ type: "text", text: JSON.stringify(result) }] };
    }
    default:
      throw new Error(`Unknown tool: ${name}`);
  }
});

const transport = new StdioServerTransport();
await server.connect(transport);
```

### package.json for MCP Server

```json
{
  "name": "@launchapp-dev/mcp-<tool-name>",
  "version": "1.0.0",
  "type": "module",
  "bin": { "mcp-<tool-name>": "dist/index.js" },
  "scripts": {
    "build": "tsc",
    "start": "node dist/index.js"
  },
  "dependencies": {
    "@modelcontextprotocol/sdk": "^1.0.0"
  },
  "devDependencies": {
    "typescript": "^5.0.0"
  }
}
```

### Using Custom MCP in AO Workflows

In the example's `mcp-servers.yaml`:
```yaml
mcp_servers:
  replicate:
    command: node
    args: ["../../mcp-servers/replicate/dist/index.js"]
    env:
      REPLICATE_API_TOKEN: "${REPLICATE_API_TOKEN}"
```

Or if published to npm:
```yaml
mcp_servers:
  replicate:
    command: npx
    args: ["-y", "@launchapp-dev/mcp-replicate"]
    env:
      REPLICATE_API_TOKEN: "${REPLICATE_API_TOKEN}"
```

### Known MCP Servers (npm)

| Package | What It Does |
|---|---|
| `@modelcontextprotocol/server-filesystem` | Read/write local files |
| `@modelcontextprotocol/server-sequential-thinking` | Structured reasoning |
| `gh-cli-mcp` | GitHub operations via gh CLI |
| `@playwright/mcp` | Browser automation |
| `@upstash/context7-mcp` | Documentation lookup |

---

## Project Layout

```
ao-examples/
├── .ao/workflows/          # Meta-workflows (the factory itself)
│   ├── agents.yaml         # conductor, master-builder, reviewer, researcher, mcp-builder
│   ├── phases.yaml         # conductor-sweep, build-example, build-mcp, review, etc.
│   ├── workflows.yaml      # conductor-loop, generate-example, build-mcp, ideation, research
│   ├── mcp-servers.yaml    # MCP server declarations for this repo
│   └── schedules.yaml      # conductor every 30min, weekly audit
├── examples/               # Generated example repos (each is standalone)
│   ├── blog-generator/     # Each has its own .ao/, README, CLAUDE.md
│   ├── stock-trader/
│   └── ...
├── mcp-servers/            # Custom-built MCP servers (each is standalone npm package)
│   ├── replicate/          # Wraps Replicate API
│   ├── elevenlabs/         # Wraps ElevenLabs API
│   └── ...
├── research/               # Tool/API/MCP research briefs
├── registry.yaml           # Master registry of all examples + status
└── CLAUDE.md
```

## Agents

| Agent | Model | Role |
|---|---|---|
| **conductor** | claude-opus-4-6 | Brain — ideates, researches, queues, manages everything |
| **master-builder** | claude-sonnet-4-6 | Builds complete example repos |
| **reviewer** | claude-sonnet-4-6 | Validates quality before shipping |
| **researcher** | claude-haiku-4-5 | Deep-dives into tools, APIs, MCP servers |
| **mcp-builder** | claude-sonnet-4-6 | Builds custom MCP servers when none exist |

## Source Material

300 pipeline use cases across 30 verticals:
`/Users/samishukri/brain/knowledge/yc/100-pipelines.md`

## Rules

- Conductor runs fully autopilot — no human intervention needed
- Each example must be a complete, runnable AO project
- Examples must demonstrate AO as GENERAL-PURPOSE, not just a coding tool
- When no MCP server exists for a needed tool, BUILD one (don't fake it)
- Custom MCP servers go in mcp-servers/ and get their own GitHub repo
- All example repos are public under launchapp-dev org: ao-example-<id>
- All MCP server repos are public under launchapp-dev org: mcp-<name>
- Use `ao queue enqueue` to dispatch work, NOT `ao task create`
- Task title = example id = directory name (this convention is critical)
- Don't queue more than 10 tasks in a single sweep
