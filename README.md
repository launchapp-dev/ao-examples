# AO Examples

Showcase repository demonstrating AO workflows across 10+ verticals. Each example is a standalone repo you can clone and run with `ao daemon start`.

## Examples

| Example | Vertical | What It Does | AO Features |
|---|---|---|---|
| [blog-generator](examples/blog-generator/) | Content | Research, outline, draft, edit, SEO optimize, publish | Multi-agent pipeline, rework loops, web search MCP, schedules |
| [story-writer](examples/story-writer/) | Creative | World-building, characters, plot, chapters, continuity review | Agent memory, multi-model routing, manual gates, output contracts |
| [researcher](examples/researcher/) | Research | Question decomposition, source gathering, analysis, synthesis | Web search MCP, structured output, decision contracts |
| [stock-trader](examples/stock-trader/) | Finance | Market data, technical analysis, risk assessment, signals | Scheduled workflows, command phases, decision contracts, multi-agent debate |
| [research-analyst](examples/research-analyst/) | Business | Market research, competitive analysis, trend reports | Web search + sequential thinking MCP, scheduled reports |
| [biology-lab](examples/biology-lab/) | Science | Literature review, hypothesis, experiment design, paper drafting | Specialized agents, manual gates, citations |
| [legal-reviewer](examples/legal-reviewer/) | Legal | Clause extraction, risk flagging, compliance, redline suggestions | Filesystem MCP, decision contracts, multi-agent review |
| [data-pipeline](examples/data-pipeline/) | Data | Source discovery, schema inference, transforms, validation | Command phases, retry policies, output contracts |
| [podcast-producer](examples/podcast-producer/) | Media | Topic research, script writing, show notes, social posts | Workflow composition, scheduled production, post-success hooks |
| [devops-automator](examples/devops-automator/) | Infrastructure | Audit, IaC generation, security review, apply | Command phases, manual approval gates, tools allowlist |

## Quick Start

```bash
# Clone a single example
git clone https://github.com/launchapp-dev/ao-examples
cd ao-examples/examples/blog-generator

# Run it
ao daemon start
```

## How This Repo Works

This repo uses AO to generate AO examples (yes, it's recursive). The meta-workflow in `.ao/workflows/` reads from `registry.yaml` and generates complete example repos.

```bash
# Generate the next pending example
ao task create "blog-generator" --workflow generate-example

# Generate all pending examples (daemon picks them up)
ao daemon start
```

## License

Elastic License 2.0 (ELv2)
