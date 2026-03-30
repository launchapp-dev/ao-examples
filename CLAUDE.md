# AO Examples

This repo generates and maintains AO workflow example repositories across verticals.

## Structure

```
ao-examples/
├── .ao/workflows/          # Meta-workflows that generate examples
├── examples/               # Generated example repos (each is a standalone repo)
│   ├── blog-generator/
│   ├── story-writer/
│   ├── researcher/
│   ├── stock-trader/
│   ├── research-analyst/
│   ├── biology-lab/
│   └── ...
├── registry.yaml           # Registry of all examples with metadata
└── CLAUDE.md
```

## How It Works

1. The `generate-example` workflow takes a vertical name and creates a complete example repo
2. Each example repo is self-contained with its own `.ao/workflows/`, `README.md`, and supporting files
3. The `refresh-examples` workflow updates all existing examples when AO workflow schema changes
4. Examples are nested repos — each can be cloned and used independently

## Rules

- Each example must be a complete, runnable AO project
- Every example needs a clear README explaining what it does and how to use it
- Workflows should demonstrate real AO features: multi-agent, phases, schedules, MCP servers
- Keep examples focused — one vertical per repo, not a kitchen sink
- Use different models/tools across examples to showcase multi-model routing
