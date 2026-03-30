# AO Examples — Autopilot Factory

This repo is an autonomous factory that generates AO workflow example repositories across verticals.
It runs fully on autopilot — an Opus conductor manages the entire operation.

## How It Works

1. **Conductor (Opus)** runs every 30 minutes via daemon schedule
2. Conductor reads registry.yaml, checks progress, ideates new examples, queues tasks
3. Each queued example triggers the `generate-example` workflow
4. Master builder creates complete repos with .ao/ config, README, supporting files
5. Reviewer validates quality → rework loop if needed
6. Completed examples get initialized as standalone git repos under examples/

## Architecture

```
ao-examples/
├── .ao/workflows/          # Meta-workflows (the factory itself)
│   ├── agents.yaml         # conductor, master-builder, reviewer, researcher
│   ├── phases.yaml         # conductor-sweep, build-example, review, etc.
│   ├── workflows.yaml      # conductor-loop, generate-example, ideation, research
│   └── schedules.yaml      # conductor every 30min, weekly audit
├── examples/               # Generated example repos (each is standalone)
│   ├── blog-generator/     # Each has its own .ao/, README, CLAUDE.md
│   ├── stock-trader/
│   └── ...
├── research/               # Tool/API research briefs from researcher agent
├── registry.yaml           # Master registry of all examples + status
└── CLAUDE.md
```

## Source Material

There are 300 documented pipeline use cases across 30 verticals in the brain repo:
`/Users/samishukri/brain/knowledge/yc/100-pipelines.md`

The conductor should reference this file for ideas. Verticals covered:
Software Engineering, Media Production, Content & Publishing, Data & Analytics,
DevOps & Infrastructure, Legal & Compliance, Customer Operations, Research & Science,
Business Operations, E-Commerce & Retail, Healthcare & Biotech, Education & Training,
Finance & Banking, Real Estate & Construction, Manufacturing & Supply Chain,
Government & Public Sector, Energy & Sustainability, Cybersecurity,
Nonprofit & Social Impact, Logistics & Transportation, Agriculture & Food,
Automotive, Telecommunications, Aviation & Aerospace, Sports & Entertainment,
Travel & Hospitality, Insurance, Media & Advertising, Pharmaceutical,
Personal & Consumer.

## Agents

| Agent | Model | Role |
|---|---|---|
| **conductor** | claude-opus-4-6 | Brain — ideates, researches, queues, manages everything |
| **master-builder** | claude-sonnet-4-6 | Builds complete example repos |
| **reviewer** | claude-sonnet-4-6 | Validates quality before shipping |
| **researcher** | claude-haiku-4-5 | Deep-dives into tools, APIs, MCP servers |

## Rules

- Conductor runs fully autopilot — no human intervention needed
- Each example must be a complete, runnable AO project
- Examples must demonstrate AO as GENERAL-PURPOSE, not just a coding tool
- Use variety: different models, MCP servers, verticals, AO features across examples
- The conductor should reference the 300 pipelines list for ideas
- Don't queue more than 3 tasks at a time
- Research real tools and integrations — no fake APIs
