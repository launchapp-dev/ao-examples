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
| [story-writer](examples/story-writer/) | Creative | World-building → characters → plot → chapters → review | generated | [repo](https://github.com/launchapp-dev/ao-example-story-writer) |
| [stock-trader](examples/stock-trader/) | Finance | Market data → bull/bear debate → risk → rebalancing | generated | [repo](https://github.com/launchapp-dev/ao-example-stock-trader) |
| [legal-reviewer](examples/legal-reviewer/) | Legal | Clause extraction → risk flagging → compliance → redlines | generated | [repo](https://github.com/launchapp-dev/ao-example-legal-reviewer) |
| [data-pipeline](examples/data-pipeline/) | Data | Source discovery → schema → transforms → validation | generated | [repo](https://github.com/launchapp-dev/ao-example-data-pipeline) |
| [podcast-producer](examples/podcast-producer/) | Media | Research → script → show notes → social posts | generated | [repo](https://github.com/launchapp-dev/ao-example-podcast-producer) |
| [threat-intel](examples/threat-intel/) | Cybersecurity | IOC collection → enrichment → correlation → analyst briefs | generated | [repo](https://github.com/launchapp-dev/ao-example-threat-intel) |
| [supply-chain-monitor](examples/supply-chain-monitor/) | Manufacturing | Supplier monitoring → disruption detection → response | generated | [repo](https://github.com/launchapp-dev/ao-example-supply-chain-monitor) |
| [grant-writer](examples/grant-writer/) | Nonprofit | Opportunity scan → proposal draft → budget → review | generated | [repo](https://github.com/launchapp-dev/ao-example-grant-writer) |
| [researcher](examples/researcher/) | Research | Question → sources → analysis → synthesis → report | generated | [repo](https://github.com/launchapp-dev/ao-example-researcher) |
| [product-catalog](examples/product-catalog/) | E-Commerce | Product data → SEO descriptions → translation → QA | generated | [repo](https://github.com/launchapp-dev/ao-example-product-catalog) |
| [curriculum-builder](examples/curriculum-builder/) | Education | Learning objectives → modules → content → quizzes → review | generated | [repo](https://github.com/launchapp-dev/ao-example-curriculum-builder) |
| [research-analyst](examples/research-analyst/) | Business | Market research → competitive analysis → trend reports | generated | [repo](https://github.com/launchapp-dev/ao-example-research-analyst) |
| [biology-lab](examples/biology-lab/) | Science | Literature → hypothesis → experiment design → paper | generated | [repo](https://github.com/launchapp-dev/ao-example-biology-lab) |
| [devops-automator](examples/devops-automator/) | Infrastructure | Audit → IaC generation → security review → apply | generated | [repo](https://github.com/launchapp-dev/ao-example-devops-automator) |
| [property-analyzer](examples/property-analyzer/) | Real Estate | Listing analysis → market comps → investment reports | generated | [repo](https://github.com/launchapp-dev/ao-example-property-analyzer) |
| [patient-intake](examples/patient-intake/) | Healthcare | Form processing → triage → provider matching → scheduling | generated | [repo](https://github.com/launchapp-dev/ao-example-patient-intake) |
| [hiring-pipeline](examples/hiring-pipeline/) | Business Ops | Job desc → screen → interview → feedback → offer | generated | [repo](https://github.com/launchapp-dev/ao-example-hiring-pipeline) |
| [event-producer](examples/event-producer/) | Entertainment | Concept → venue → talent → marketing → runsheet | generated | [repo](https://github.com/launchapp-dev/ao-example-event-producer) |
| [invoice-processor](examples/invoice-processor/) | Finance Ops | Extract → match PO → validate → approve → reconcile | generated | [repo](https://github.com/launchapp-dev/ao-example-invoice-processor) |
| [fleet-dispatcher](examples/fleet-dispatcher/) | Logistics | Orders → route optimization → dispatch → exceptions → report | generated | [repo](https://github.com/launchapp-dev/ao-example-fleet-dispatcher) |
| [energy-auditor](examples/energy-auditor/) | Energy | Consumption analysis → benchmarking → savings → audit report | generated | [repo](https://github.com/launchapp-dev/ao-example-energy-auditor) |
| [travel-planner](examples/travel-planner/) | Travel | Destinations → itinerary → budget → packing list | generated | [repo](https://github.com/launchapp-dev/ao-example-travel-planner) |
| [claims-processor](examples/claims-processor/) | Insurance | Intake → coverage check → fraud detection → settlement | generated | [repo](https://github.com/launchapp-dev/ao-example-claims-processor) |
| [ad-campaign](examples/ad-campaign/) | Advertising | Audience research → creative brief → copy → A/B test → launch | generated | [repo](https://github.com/launchapp-dev/ao-example-ad-campaign) |
| [crop-monitor](examples/crop-monitor/) | Agriculture | Field data → disease detection → treatment → dispatch | generated | [repo](https://github.com/launchapp-dev/ao-example-crop-monitor) |
| [foia-processor](examples/foia-processor/) | Government | Records request → search → redact → legal review → release | generated | [repo](https://github.com/launchapp-dev/ao-example-foia-processor) |
| [vehicle-recall](examples/vehicle-recall/) | Automotive | Defect pattern → VIN scope → notification → repair tracking | generated | [repo](https://github.com/launchapp-dev/ao-example-vehicle-recall) |
| [network-fault-manager](examples/network-fault-manager/) | Telecom | Alarm correlation → diagnosis → dispatch → RCA report | generated | [repo](https://github.com/launchapp-dev/ao-example-network-fault-manager) |
| [pharmacovigilance](examples/pharmacovigilance/) | Pharma | Adverse event monitoring → causality → signal detection → regulatory | generated | [repo](https://github.com/launchapp-dev/ao-example-pharmacovigilance) |
| [athlete-tracker](examples/athlete-tracker/) | Sports | Biometrics → workload trends → injury risk → load management | generated | [repo](https://github.com/launchapp-dev/ao-example-athlete-tracker) |
| [satellite-ops](examples/satellite-ops/) | Aerospace | Telemetry monitoring → orbit maintenance → anomaly response | generated | [repo](https://github.com/launchapp-dev/ao-example-satellite-ops) |
| [personal-finance](examples/personal-finance/) | Consumer | Transaction analysis → budgeting → investment recommendations | generated | [repo](https://github.com/launchapp-dev/ao-example-personal-finance) |
| [game-narrative](examples/game-narrative/) | Gaming | World-building → dialogue trees → branching logic → continuity | generated | [repo](https://github.com/launchapp-dev/ao-example-game-narrative) |
| [support-triage](examples/support-triage/) | Customer Ops | Ticket classification → routing → response drafts → analytics | generated | [repo](https://github.com/launchapp-dev/ao-example-support-triage) |
| [recipe-developer](examples/recipe-developer/) | Food | Nutritional targets → recipe generation → cost analysis → publish | generated | [repo](https://github.com/launchapp-dev/ao-example-recipe-developer) |
| [construction-tracker](examples/construction-tracker/) | Construction | Schedule tracking → delay detection → resource reallocation | generated | [repo](https://github.com/launchapp-dev/ao-example-construction-tracker) |
| [content-moderator](examples/content-moderator/) | Trust & Safety | AI classification → human review → appeals → analytics | generated | [repo](https://github.com/launchapp-dev/ao-example-content-moderator) |
| [immigration-tracker](examples/immigration-tracker/) | Immigration | Eligibility → documents → filing → status tracking → RFEs | generated | [repo](https://github.com/launchapp-dev/ao-example-immigration-tracker) |
| [clinical-trial](examples/clinical-trial/) | Biotech | Protocol design → recruitment → monitoring → analysis → submission | generated | [repo](https://github.com/launchapp-dev/ao-example-clinical-trial) |
| [incident-responder](examples/incident-responder/) | SRE | Alert detection → diagnosis → mitigation → RCA → postmortem | generated | [repo](https://github.com/launchapp-dev/ao-example-incident-responder) |
| [esg-reporter](examples/esg-reporter/) | Sustainability | ESG metrics → benchmarking → GRI/SASB reports → assurance | generated | [repo](https://github.com/launchapp-dev/ao-example-esg-reporter) |
| [tax-preparer](examples/tax-preparer/) | Finance | Document gathering → deductions → tax calculation → filing | generated | [repo](https://github.com/launchapp-dev/ao-example-tax-preparer) |
| [compliance-auditor](examples/compliance-auditor/) | Customs & Trade | HS classification → duty rates → customs declarations → filing | generated | [repo](https://github.com/launchapp-dev/ao-example-compliance-auditor) |
| [donor-prospector](examples/donor-prospector/) | Nonprofit | Prospect research → scoring → outreach → stewardship → analytics | generated | [repo](https://github.com/launchapp-dev/ao-example-donor-prospector) |
| [brand-monitor](examples/brand-monitor/) | Marketing Intelligence | Social monitoring → sentiment analysis → crisis detection → response drafts → brand health reports | generated | [repo](https://github.com/launchapp-dev/ao-example-brand-monitor) |
| [loan-originator](examples/loan-originator/) | Banking | Application → credit check → underwriting → approval → closing docs | generated | [repo](https://github.com/launchapp-dev/ao-example-loan-originator) |
| [college-advisor](examples/college-advisor/) | Education | School research → essay writing → deadline tracking → financial aid → offers | generated | [repo](https://github.com/launchapp-dev/ao-example-college-advisor) |
| [permit-tracker](examples/permit-tracker/) | Government | Requirements → application → submission → corrections → inspections | generated | [repo](https://github.com/launchapp-dev/ao-example-permit-tracker) |
| [fraud-detector](examples/fraud-detector/) | Finance / Compliance | Transaction monitoring → anomaly scoring → investigation → SARs | generated | [repo](https://github.com/launchapp-dev/ao-example-fraud-detector) |
| [warehouse-optimizer](examples/warehouse-optimizer/) | Warehouse Ops | Pick pattern analysis → slotting optimization → move plans → efficiency dashboards | generated | [repo](https://github.com/launchapp-dev/ao-example-warehouse-optimizer) |
| [ma-due-diligence](workflows/ma-due-diligence/) | Corporate Finance | Document collection → financial/tech/legal analysis → investment memo | generated | [repo](https://github.com/launchapp-dev/ao-example-ma-due-diligence) |
| [drug-discovery](workflows/drug-discovery/) | Pharma R&D | Target ID → compound screening → lead optimization → IND filing | generated | [repo](https://github.com/launchapp-dev/ao-example-drug-discovery) |
| [hotel-revenue](workflows/hotel-revenue/) | Hospitality | Demand forecast → rate optimization → competitor monitoring → revenue report | generated | [repo](https://github.com/launchapp-dev/ao-example-hotel-revenue) |
| [wedding-planner](workflows/wedding-planner/) | Consumer Events | Vision → venues → vendors → budget → invitations → day-of timeline | generated | [repo](https://github.com/launchapp-dev/ao-example-wedding-planner) |
| [video-factory](workflows/video-factory/) | Media Production | Trend research → script → creative review → thumbnails → SEO | generated | [repo](https://github.com/launchapp-dev/ao-example-video-factory) |
| [estate-planner](workflows/estate-planner/) | Personal Legal | Asset inventory → trust/will drafting → tax optimization → legal review | generated | [repo](https://github.com/launchapp-dev/ao-example-estate-planner) |
| [home-renovation](workflows/home-renovation/) | Consumer / Home | Contractor vetting → permit tracking → construction management → inspections | generated | [repo](https://github.com/launchapp-dev/ao-example-home-renovation) |
| [restaurant-ops](workflows/restaurant-ops/) | Food & Hospitality | Menu planning → food costing → prep scheduling → waste tracking → daily P&L | generated | [repo](https://github.com/launchapp-dev/ao-example-restaurant-ops) |

| [fitness-coach](examples/fitness-coach/) | Consumer Health | Baseline assessment → periodized programming → daily workouts → progress tracking | generated | [repo](https://github.com/launchapp-dev/ao-example-fitness-coach) |
| aml-monitor | Banking Compliance | Transaction screening → pattern detection → SAR filing → case management | queued | — |
| dynamic-pricer | E-Commerce Analytics | Competitor monitoring → demand elasticity → A/B testing → price optimization | queued | — |
| emergency-manager | Government / Crisis | Disaster detection → alerts → resource mobilization → situation reports → recovery | queued | — |
| [influencer-campaign](examples/influencer-campaign/) | Marketing / Social | Talent discovery → vetting → creative briefs → content review → ROI analysis | generated | [repo](https://github.com/launchapp-dev/ao-example-influencer-campaign) |

*64 examples across 60 verticals — 61 generated, 3 queued. More added autonomously by the conductor every 30 minutes.*

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
