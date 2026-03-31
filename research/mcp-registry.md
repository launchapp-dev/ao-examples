# MCP Server Registry — Real, Working Servers

> Last updated: 2026-03-30
> Only servers verified to exist on npm or GitHub with recent activity.

## Official (@modelcontextprotocol)

| Package | Command | What It Does |
|---|---|---|
| `@modelcontextprotocol/server-filesystem` | `npx -y @modelcontextprotocol/server-filesystem /path` | Read/write files, list dirs, search |
| `@modelcontextprotocol/server-fetch` | `npx -y @modelcontextprotocol/server-fetch` | Fetch web content, HTML→markdown |
| `@modelcontextprotocol/server-git` | `npx -y @modelcontextprotocol/server-git` | Git operations: clone, commit, diff, log, push |
| `@modelcontextprotocol/server-memory` | `npx -y @modelcontextprotocol/server-memory` | Persistent knowledge graph memory |
| `@modelcontextprotocol/server-sequential-thinking` | `npx -y @modelcontextprotocol/server-sequential-thinking` | Structured reasoning chains |
| `@modelcontextprotocol/server-postgres` | `npx -y @modelcontextprotocol/server-postgres` | Read-only PostgreSQL queries |
| `@modelcontextprotocol/server-slack` | `npx -y @modelcontextprotocol/server-slack` | Read channels, post messages, thread summaries |
| `@modelcontextprotocol/server-gitlab` | `npx -y @modelcontextprotocol/server-gitlab` | GitLab repos, issues, merge requests |
| `@modelcontextprotocol/server-time` | `npx -y @modelcontextprotocol/server-time` | Time and timezone operations |

## Vendor (Official Product Servers)

| Package | Command | What It Does | API Key |
|---|---|---|---|
| `figma-developer-mcp` | `npx -y figma-developer-mcp` | Figma design access — layers, auto-layout, variants, styles | FIGMA_PERSONAL_ACCESS_TOKEN |
| `@notionhq/notion-mcp-server` | `npx -y @notionhq/notion-mcp-server` | Notion pages, databases, search | NOTION_TOKEN |
| `gh-cli-mcp` | `npx -y gh-cli-mcp` | GitHub via gh CLI — issues, PRs, repos | GH_TOKEN (or gh auth) |
| `@playwright/mcp` | `npx -y @playwright/mcp --headless` | Browser automation — navigate, click, screenshot, scrape | None |

## Community (Popular, Maintained)

| Package | Command | What It Does | API Key |
|---|---|---|---|
| `@tacticlaunch/mcp-linear` | `npx -y @tacticlaunch/mcp-linear` | Linear issues, projects, teams | LINEAR_API_KEY |
| `@berthojoris/mcp-sqlite-server` | `npx -y @berthojoris/mcp-sqlite-server` | SQLite CRUD operations | None |
| `@upstash/context7-mcp` | `npx -y @upstash/context7-mcp` | Documentation lookup | None |

## Search Servers

| Package | Command | What It Does | API Key |
|---|---|---|---|
| Brave Search | See brave/brave-search-mcp-server on GitHub | Web, image, video, news search | BRAVE_API_KEY |
| `@modelcontextprotocol/server-fetch` | `npx -y @modelcontextprotocol/server-fetch` | Fetch any URL, convert to markdown | None |

## Database Servers

| Package | Command | What It Does |
|---|---|---|
| `@modelcontextprotocol/server-postgres` | `npx -y @modelcontextprotocol/server-postgres` | PostgreSQL read-only |
| `@berthojoris/mcp-sqlite-server` | `npx -y @berthojoris/mcp-sqlite-server` | SQLite full CRUD |
| `@executeautomation/mcp-database-server` | `npx -y @executeautomation/mcp-database-server` | SQLite, SQL Server, PostgreSQL, MySQL |

## High-Value Combinations for Workflows

### Blog/Content Generator
- `server-fetch` (research web content) + `server-filesystem` (write markdown) + `server-memory` (remember context)

### Design System Builder
- `figma-developer-mcp` (read Figma designs) + `server-filesystem` (generate code/tokens)

### Project Management Automation
- `gh-cli-mcp` (GitHub) + `@tacticlaunch/mcp-linear` (Linear) + `server-slack` (notifications)

### Research Pipeline
- `server-fetch` (web research) + `server-sequential-thinking` (analysis) + `server-filesystem` (reports)

### Data Pipeline
- `server-postgres` (read data) + `server-filesystem` (write reports) + `server-fetch` (enrich)

### Website Monitor
- `@playwright/mcp` (scrape/screenshot) + `server-filesystem` (save results) + cron schedule

## Directories to Find More
- https://registry.modelcontextprotocol.io/
- https://www.pulsemcp.com/servers (10,940+ servers)
- https://github.com/wong2/awesome-mcp-servers
- https://mcp.so/
