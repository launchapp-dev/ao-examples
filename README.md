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
| [aml-monitor](workflows/aml-monitor/) | Banking Compliance | Transaction screening → pattern detection → SAR filing → case management | generated | [repo](https://github.com/launchapp-dev/ao-example-aml-monitor) |
| [dynamic-pricer](workflows/dynamic-pricer/) | E-Commerce Analytics | Competitor monitoring → demand elasticity → A/B testing → price optimization | generated | [repo](https://github.com/launchapp-dev/ao-example-dynamic-pricer) |
| [emergency-manager](workflows/emergency-manager/) | Government / Crisis | Disaster detection → alerts → resource mobilization → situation reports → recovery | generated | [repo](https://github.com/launchapp-dev/ao-example-emergency-manager) |
| [influencer-campaign](examples/influencer-campaign/) | Marketing / Social | Talent discovery → vetting → creative briefs → content review → ROI analysis | generated | [repo](https://github.com/launchapp-dev/ao-example-influencer-campaign) |
| [accreditation-tracker](examples/accreditation-tracker/) | Education Compliance | Standards mapping → evidence collection → gap analysis → self-study report | generated | [repo](https://github.com/launchapp-dev/ao-example-accreditation-tracker) |
| [water-quality-monitor](examples/water-quality-monitor/) | Environmental | Sensor ingestion → trend analysis → EPA compliance → remediation → regulatory filing | generated | [repo](https://github.com/launchapp-dev/ao-example-water-quality-monitor) |
| [freight-broker](examples/freight-broker/) | Logistics / Freight | Carrier matching → rate negotiation → BOL generation → tracking → settlement | generated | [repo](https://github.com/launchapp-dev/ao-example-freight-broker) |
| [insurance-onboarding](examples/insurance-onboarding/) | Insurance Ops | License verification → background checks → training → provisioning → certification | generated | [repo](https://github.com/launchapp-dev/ao-example-insurance-onboarding) |
| [parts-catalog](examples/parts-catalog/) | Automotive Manufacturing | ECO processing → fitment updates → diagram generation → translation → publishing | generated | [repo](https://github.com/launchapp-dev/ao-workflow-parts-catalog) |
| [meal-planner](examples/meal-planner/) | Consumer Food | Dietary preferences → recipe matching → grocery lists → batch cooking → cost tracking | generated | [repo](https://github.com/launchapp-dev/ao-workflow-meal-planner) |
| [aircraft-maintenance](examples/aircraft-maintenance/) | Aviation | Flight hour tracking → inspection scheduling → work orders → airworthiness certification | generated | [repo](https://github.com/launchapp-dev/ao-workflow-aircraft-maintenance) |
| [esports-tournament](examples/esports-tournament/) | Esports | Registration → bracket seeding → match scheduling → disputes → prize distribution | generated | [repo](https://github.com/launchapp-dev/ao-workflow-esports-tournament) |
| [music-producer](examples/music-producer/) | Media / Music | Album concept → lyrics → composition → mastering → artwork → distribution | generated | [repo](https://github.com/launchapp-dev/ao-workflow-music-producer) |
| [home-buyer](examples/home-buyer/) | Consumer Real Estate | Financial readiness → mortgage → house hunting → offers → closing | generated | [repo](https://github.com/launchapp-dev/ao-workflow-home-buyer) |
| [subtitle-pipeline](examples/subtitle-pipeline/) | Media / Localization | Transcription → translation → timing sync → dubbed voiceover → SRT/VTT | generated | [repo](https://github.com/launchapp-dev/ao-workflow-subtitle-pipeline) |
| [pet-care](examples/pet-care/) | Consumer Pet Care | Vaccination tracking → weight monitoring → medication → vet appointments → wellness | generated | [repo](https://github.com/launchapp-dev/ao-workflow-pet-care) |
| [changelog-generator](examples/changelog-generator/) | Developer Tools | Git history → commit categorization → release notes → migration guides → GitHub release | generated | [repo](https://github.com/launchapp-dev/ao-workflow-changelog-generator) |
| [repo-health-checker](examples/repo-health-checker/) | Developer Tools | Org-wide repo audit → stale PRs → missing CI → security advisories → scorecards | generated | [repo](https://github.com/launchapp-dev/ao-workflow-repo-health-checker) |
| [slack-digest](examples/slack-digest/) | Business Ops | Channel monitoring → topic clustering → daily digest → action items → archive | generated | [repo](https://github.com/launchapp-dev/ao-workflow-slack-digest) |
| [notion-wiki-sync](examples/notion-wiki-sync/) | Knowledge Mgmt | Notion page scanning → staleness detection → code cross-ref → markdown export | generated | [repo](https://github.com/launchapp-dev/ao-workflow-notion-wiki-sync) |
| [api-docs-generator](examples/api-docs-generator/) | Developer Tools | Route parsing → schema extraction → example generation → validation → OpenAPI | generated | [repo](https://github.com/launchapp-dev/ao-workflow-api-docs-generator) |
| [food-safety-auditor](examples/food-safety-auditor/) | Food Safety | HACCP checklists → facility inspections → corrective actions → compliance reports | generated | [repo](https://github.com/launchapp-dev/ao-example-food-safety-auditor) |
| [food-waste-tracker](examples/food-waste-tracker/) | Sustainability | Inventory tracking → spoilage prediction → donations → impact reports | generated | [repo](https://github.com/launchapp-dev/ao-workflow-food-waste-tracker) |
| [guest-experience](examples/guest-experience/) | Hospitality | Guest profiling → room personalization → service coordination → satisfaction | generated | [repo](https://github.com/launchapp-dev/ao-workflow-guest-experience) |
| [dependency-updater](examples/dependency-updater/) | Developer Tools / CI-CD | Dependency scanning → risk assessment → update PRs → test validation | generated | [repo](https://github.com/launchapp-dev/ao-workflow-dependency-updater) |
| [seo-auditor](examples/seo-auditor/) | Marketing / SEO | Site crawling → on-page analysis → Core Web Vitals → competitor comparison | generated | [repo](https://github.com/launchapp-dev/ao-workflow-seo-auditor) |
| [meeting-summarizer](examples/meeting-summarizer/) | Business Productivity | Transcript processing → topic extraction → action items → Linear tasks | generated | [repo](https://github.com/launchapp-dev/ao-workflow-meeting-summarizer) |
| [license-compliance](examples/license-compliance/) | Legal / DevTools | Dependency license scanning → conflict detection → remediation → compliance reports | generated | [repo](https://github.com/launchapp-dev/ao-workflow-license-compliance) |
| [board-deck-generator](examples/board-deck-generator/) | Business Executive | Metrics collection → narrative writing → slide design → executive review | generated | [repo](https://github.com/launchapp-dev/ao-workflow-board-deck-generator) |
| [tenant-screening](examples/tenant-screening/) | Real Estate | Application processing → credit/background checks → scoring → lease generation | generated | [repo](https://github.com/launchapp-dev/ao-workflow-tenant-screening) |
| [code-review-bot](examples/code-review-bot/) | Developer Tools | PR analysis → code quality → security scan → review comments → approval | generated | [repo](https://github.com/launchapp-dev/ao-workflow-code-review-bot) |
| [inventory-forecaster](examples/inventory-forecaster/) | Retail | Demand modeling → safety stock → reorder triggers → purchase orders | generated | [repo](https://github.com/launchapp-dev/ao-workflow-inventory-forecaster) |
| [social-media-scheduler](examples/social-media-scheduler/) | Marketing / Social | Content strategy → copy writing → image gen → scheduling → analytics | generated | [repo](https://github.com/launchapp-dev/ao-workflow-social-media-scheduler) |
| [newsletter-factory](examples/newsletter-factory/) | Content Marketing | Topic curation → writing → design → audience segmentation → send | generated | [repo](https://github.com/launchapp-dev/ao-workflow-newsletter-factory) |
| [vulnerability-scanner](examples/vulnerability-scanner/) | Cybersecurity / DevTools | Dependency scan → CVE enrichment → severity ranking → remediation PRs | generated | [repo](https://github.com/launchapp-dev/ao-workflow-vulnerability-scanner) |
| [vendor-evaluator](examples/vendor-evaluator/) | Business Ops | Requirements → RFI → score responses → negotiate → contract → onboard | generated | [repo](https://github.com/launchapp-dev/ao-workflow-vendor-evaluator) |
| [runbook-generator](examples/runbook-generator/) | DevOps / SRE | Incident analysis → procedure docs → test runbook → publish → train | generated | [repo](https://github.com/launchapp-dev/ao-workflow-runbook-generator) |
| [assignment-grader](examples/assignment-grader/) | Education | Submission collection → auto-grade → plagiarism check → feedback → record | generated | [repo](https://github.com/launchapp-dev/ao-workflow-assignment-grader) |
| [data-quality-monitor](examples/data-quality-monitor/) | Data Analytics | Data profiling → anomaly detection → auto-fix → alerting → reports | generated | [repo](https://github.com/launchapp-dev/ao-workflow-data-quality-monitor) |
| [price-tracker](examples/price-tracker/) | E-Commerce / Consumer | Product scraping → price comparison → trend analysis → deal alerts | generated | [repo](https://github.com/launchapp-dev/ao-workflow-price-tracker) |
| [customer-segmentation](examples/customer-segmentation/) | Data Analytics / Marketing | Behavioral clustering → segment profiling → persona generation → strategy recommendations | generated | [repo](https://github.com/launchapp-dev/ao-workflow-customer-segmentation) |
| [volunteer-coordinator](examples/volunteer-coordinator/) | Nonprofit Ops | Application screening → opportunity matching → onboarding → shift scheduling → impact reports | generated | [repo](https://github.com/launchapp-dev/ao-workflow-volunteer-coordinator) |
| [telecom-billing-resolver](examples/telecom-billing-resolver/) | Telecom | Billing dispute resolution → CDR parsing → credit eligibility → resolution letters | generated | [repo](https://github.com/launchapp-dev/ao-example-telecom-billing-resolver) |
| [campaign-bid-optimizer](examples/campaign-bid-optimizer/) | Advertising | Performance data → metrics → segment analysis → bid adjustments → budget reallocation | generated | [repo](https://github.com/launchapp-dev/ao-workflow-campaign-bid-optimizer) |
| [ev-charging-planner](examples/ev-charging-planner/) | Automotive Infrastructure | Geographic coverage gaps → site evaluation → scoring → assessment reports → permitting | generated | [repo](https://github.com/launchapp-dev/ao-workflow-ev-charging-planner) |
| [budget-planner](examples/budget-planner/) | Finance Planning | Budget consolidation → variance analysis → threshold flagging → executive summaries → forecast adjustments | generated | [repo](https://github.com/launchapp-dev/ao-workflow-budget-planner) |
| [lease-manager](examples/lease-manager/) | Real Estate | Lease tracking → renewal proposals → rent escalations → compliance reporting | generated | [repo](https://github.com/launchapp-dev/ao-example-lease-manager) |
| [returns-processor](examples/returns-processor/) | E-Commerce Ops | Return intake → condition inspection → disposition → refund → analytics | generated | [repo](https://github.com/launchapp-dev/ao-example-returns-processor) |
| [privacy-policy-generator](examples/privacy-policy-generator/) | Legal Compliance | Data collection scanning → data flow mapping → GDPR/CCPA/COPPA policies → version control | generated | [repo](https://github.com/launchapp-dev/ao-example-privacy-policy-generator) |
| [i18n-pipeline](examples/i18n-pipeline/) | Software Engineering | String scanning → key extraction → locale validation → coverage dashboards → release gating | generated | [repo](https://github.com/launchapp-dev/ao-example-i18n-pipeline) |
| [cargo-ops](examples/cargo-ops/) | Aviation / Aerospace | Booking intake → DG classification → load planning → weight/balance → departure docs | generated | [repo](https://github.com/launchapp-dev/ao-workflow-cargo-ops) |
| [nps-followup](examples/nps-followup/) | Customer Ops | NPS survey analysis → detractor rescue → promoter engagement → response automation | generated | [repo](https://github.com/launchapp-dev/ao-workflow-nps-followup) |
| [batch-record](examples/batch-record/) | Pharma Manufacturing | Batch initiation → QC checks → deviation handling → yield calculation → QP release | generated | [repo](https://github.com/launchapp-dev/ao-example-batch-record) |
| [ticket-pricing](examples/ticket-pricing/) | Sports & Entertainment | Demand forecasting → competitor scraping → elasticity modeling → price optimization → revenue simulation | generated | [repo](https://github.com/launchapp-dev/ao-example-ticket-pricing) |
| [actuarial-modeler](examples/actuarial-modeler/) | Insurance | Risk modeling → loss triangles → reserve estimation → rate indications → filing memoranda | generated | [repo](https://github.com/launchapp-dev/ao-example-actuarial-modeler) |

*121 examples across 30+ verticals — 113 generated, 8 queued. More added autonomously by the conductor every 30 minutes.*

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
