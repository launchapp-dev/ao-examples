# AO Examples

Autonomous factory that generates AO workflow examples across 30+ verticals. Runs fully on autopilot — an Opus conductor ideates, researches, builds, and ships example repos every 30 minutes.

## How It Works

```
┌─────────────────────────────────────────────────────┐
│                 CONDUCTOR (Opus)                     │
│              runs every 30 minutes                   │
│                                                      │
│  1. Check progress on running tasks                  │
│  2. Ideate new examples (tools, APIs, verticals)     │
│  3. Research integrations (MCP servers, APIs)         │
│  4. Queue new tasks → generate-example workflow       │
│  5. Update registry + README                         │
└──────────┬──────────────────────────────┬────────────┘
           │                              │
           ▼                              ▼
┌─────────────────────┐    ┌─────────────────────────┐
│  generate-example   │    │    research workflow     │
│                     │    │                          │
│  plan → scaffold    │    │  deep-dive on tools,     │
│  → build → review   │    │  APIs, MCP servers       │
│  → init repo        │    │                          │
│  → update registry  │    │  writes to research/     │
│                     │    │                          │
│  (rework loop if    │    └─────────────────────────┘
│   review fails)     │
└─────────────────────┘
```

## Examples

> This table is updated automatically by the conductor as examples are generated.

| Example | Vertical | What It Does | Status | Repo |
|---|---|---|---|---|
| [blog-generator](examples/blog-generator/) | Content | SEO research → outline → draft → edit → publish | generated | [repo](https://github.com/launchapp-dev/ao-example-blog-generator) |
| [stock-trader](examples/stock-trader/) | Finance | Market data → bull/bear debate → risk → rebalancing | generated | [repo](https://github.com/launchapp-dev/ao-example-stock-trader) |
| [legal-reviewer](examples/legal-reviewer/) | Legal | Clause extraction → risk flagging → compliance → redlines | generated | [repo](https://github.com/launchapp-dev/ao-example-legal-reviewer) |
| story-writer | Creative | World-building → characters → plot → chapters → review | **building** | |
| podcast-producer | Media | Research → script → show notes → social posts | **building** | |
| supply-chain-monitor | Manufacturing | Supplier monitoring → disruption detection → response | **building** | |
| threat-intel | Cybersecurity | IOC collection → enrichment → correlation → analyst briefs | queued | |
| data-pipeline | Data | Source discovery → schema → transforms → validation | queued | |
| grant-writer | Nonprofit | Opportunity scan → proposal draft → budget → review | queued | |
| researcher | Research | Question → sources → analysis → synthesis → report | queued | |
| research-analyst | Business | Market research → competitive analysis → trend reports | queued | |
| biology-lab | Science | Literature → hypothesis → experiment design → paper | queued | |
| devops-automator | Infrastructure | Audit → IaC generation → security review → apply | queued | |
| property-analyzer | Real Estate | Listing analysis → market comps → investment reports | queued | |
| product-catalog | E-Commerce | Product data → SEO descriptions → translation → QA | queued | |
| patient-intake | Healthcare | Form processing → triage → provider matching → scheduling | queued | |
| curriculum-builder | Education | Learning objectives → modules → content → quizzes → review | queued | |
| hiring-pipeline | Business Ops | Job desc → screen → interview → feedback → offer | queued | |
| event-producer | Entertainment | Concept → venue → talent → marketing → runsheet | queued | |
| invoice-processor | Finance Ops | Extract → match PO → validate → approve → reconcile | queued | |
| fleet-dispatcher | Logistics | Orders → route optimization → dispatch → exceptions → report | queued | |
| energy-auditor | Energy | Consumption analysis → benchmarking → savings → audit report | queued | |

*22 examples across 22 verticals. More added autonomously by the conductor every 30 minutes.*

## Quick Start

```bash
# Clone the repo
git clone https://github.com/launchapp-dev/ao-examples
cd ao-examples

# Start the autopilot factory
ao daemon start

# Or generate a specific example manually
ao task create "blog-generator" --workflow generate-example
```

## Use a Generated Example

```bash
# Each example is a standalone AO project
cd examples/blog-generator
ao daemon start
```

## Agents

| Agent | Model | Role |
|---|---|---|
| **conductor** | Opus | Brain — runs every 30min. Ideates, researches tools, queues tasks, manages everything |
| **master-builder** | Sonnet | Builds complete example repos with .ao/ config, README, supporting files |
| **reviewer** | Sonnet | Validates quality — structure, correctness, showcase value |
| **researcher** | Haiku | Deep-dives into tools, APIs, MCP servers for new example ideas |

## Source Material

This factory draws from 300 documented pipeline use cases across 30 verticals:
- Software Engineering, Media Production, Content & Publishing
- Data & Analytics, DevOps, Legal, Customer Ops, Research, Science
- E-Commerce, Healthcare, Education, Finance, Real Estate
- Manufacturing, Government, Energy, Cybersecurity, Nonprofit
- Logistics, Agriculture, Automotive, Telecom, Aerospace
- Sports, Travel, Insurance, Advertising, Pharma, Consumer

## License

Elastic License 2.0 (ELv2)
