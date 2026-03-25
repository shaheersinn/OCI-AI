# Codex Master Architecture Spec v2 — OCI Intelligence Platform (GitHub Education Compatible)

## Read This First

This file is the master execution spec for Codex. Treat it as binding project instructions.

Your mission is to build a complete, deployable, production-style full-stack website for a Canadian OCI intelligence and simulation platform that includes:

1. Bid Strategy Optimizer
2. Firm Intelligence Briefs
3. Mock OCI Simulator
4. Cover Letter Co-pilot

The platform must eventually support these later intelligence layers:
- persistent student memory
- recruiter signal intelligence
- calibrated confidence
- counterfactual recommendations
- knowledge graph
- temporal market intelligence
- selective runtime multi-agent orchestration
- voice analysis

Do not overbuild early phases. Build the smallest stable deployable system first, then layer intelligence on top.

---

## 1) Absolute Rules

1. Use only GitHub Education-compatible or GitHub-native services for paid infrastructure unless the user explicitly approves an exception later.
2. The output must be a real, deployable website with frontend, backend, data layer, jobs, CI/CD, staging, production, and UI.
3. Before each phase, complete a Research Gate.
4. After each phase, generate a `.docx` report and a `.zip` artifact package.
5. Maintain a working deployed environment throughout the project.
6. Do not expose API keys, tokens, or provider secrets to the browser.
7. Do not introduce runtime multi-agent orchestration before its eval-based justification phase.
8. Do not pause for confirmation unless a true blocker exists.
9. Prefer official docs first for every research task.
10. Keep every recommendation auditable and reproducible.

---

## 2) Product Thesis

This product wins because it combines four monetizable student workflows in one system:

- **Bid Strategy Optimizer**: converts profile inputs into an evidence-backed bid list
- **Firm Intelligence Briefs**: generates firm-specific prep intelligence
- **Mock OCI Simulator**: gives high-frequency interview practice and scoring
- **Cover Letter Co-pilot**: rewrites letters against firm-specific hiring signals

The long-term moat comes from:
- outcome logging
- personalization
- recruiter / market signals
- confidence calibration
- counterfactual reasoning
- longitudinal cohort data
- eval-driven system improvements

---

## 3) GitHub Education Tooling Policy

### Allowed core infrastructure

Use this default stack unless a later research memo proves a better GitHub-Education-compatible option:

- GitHub repo
- GitHub Actions
- GitHub Codespaces
- GitHub Copilot Student
- GitHub Pages
- DigitalOcean credits
- Azure student credits
- Appwrite Education plan
- MongoDB Atlas credits
- Stripe student offer
- Datadog student offer
- Namecheap / Name.com domain offers

### Primary production path

Use this path first:

- **Web frontend:** Next.js + TypeScript + Tailwind + shadcn/ui
- **Backend API:** FastAPI + Pydantic + SQLAlchemy + Alembic
- **Workers:** Python worker service
- **Primary DB:** PostgreSQL + pgvector
- **Queue/cache:** Redis
- **Object storage:** S3-compatible bucket
- **Monitoring:** Datadog
- **Billing:** Stripe
- **CI/CD:** GitHub Actions
- **Dev environment:** GitHub Codespaces
- **Primary deployment:** DigitalOcean App Platform + managed DB + Redis + Spaces
- **Fallback deployment:** Azure App Service / Azure Container Apps / Azure Database as documented in the phase research

### Optional use only if it reduces delivery risk

- Appwrite Auth or Appwrite Hosting can be used only if research shows it shortens delivery materially without weakening control over the product architecture.

### Not allowed as the default hosted backbone

Do not make these the primary architecture unless a later approved exception exists:
- Vercel
- Supabase
- Clerk
- Pinecone
- Weaviate Cloud
- Railway
- Render
- arbitrary SaaS tools not covered by GitHub Education

---

## 4) End-State Definition

The project is complete only when all of the following exist:

- a public landing site
- a logged-in student dashboard
- a billing/paywall flow
- a firm intelligence interface
- a bid strategy interface
- a mock OCI session interface
- a cover letter generation interface
- an admin interface
- data ingestion jobs
- persistent database storage
- CI/CD workflows
- staging and production deployment
- observability and alerts
- phase reports and artifact packages
- operational documentation for deployment and maintenance

---

## 5) Build Philosophy

### Core principle
Build **backend-first, monorepo-first, eval-first, deployable-at-every-step**.

### Runtime philosophy
In v1, prefer:
- one web app
- one main API
- one worker service
- one main database
- one queue/cache layer

### Agent philosophy
Use many **Codex build agents** to help deliver the system, but keep the **runtime application** mostly service-based until later phases prove multi-agent runtime value.

---

## 6) Runtime Architecture

```text
Internet Users
   │
   ▼
Next.js Web App
   │
   ▼
FastAPI API / BFF
   ├── Auth + session layer
   ├── Product services
   ├── Stripe integration
   ├── Admin APIs
   └── Audit / telemetry layer
          │
          ├────────────── PostgreSQL + pgvector
          ├────────────── Redis
          ├────────────── Object Storage
          └────────────── Datadog
                               ▲
                               │
                     Python Worker / Scheduler
                       ├─ scraping
                       ├─ ingestion
                       ├─ chunking
                       ├─ embedding
                       ├─ ranking jobs
                       ├─ interview scoring jobs
                       ├─ export generation
                       └─ scheduled refresh jobs
```

---

## 7) Repository Layout

```text
oci-platform/
├─ AGENTS.md
├─ README.md
├─ LICENSE
├─ .env.example
├─ docker-compose.yml
├─ .github/
│  ├─ workflows/
│  │  ├─ ci.yml
│  │  ├─ deploy-staging.yml
│  │  ├─ deploy-production.yml
│  │  ├─ artifact-report.yml
│  │  └─ nightly-jobs.yml
│  └─ ISSUE_TEMPLATE/
├─ .codex/
│  ├─ config.toml
│  ├─ agents/
│  ├─ skills/
│  ├─ prompts/
│  └─ templates/
├─ apps/
│  ├─ web/
│  ├─ api/
│  └─ worker/
├─ packages/
│  ├─ ui/
│  ├─ prompts/
│  ├─ schemas/
│  ├─ evals/
│  ├─ config/
│  └─ client/
├─ data-pipelines/
│  ├─ nalp/
│  ├─ firms/
│  ├─ schools/
│  ├─ public-signals/
│  └─ feature-builders/
├─ infra/
│  ├─ docker/
│  ├─ deploy/
│  ├─ migrations/
│  ├─ monitoring/
│  ├─ seed/
│  └─ scripts/
├─ docs/
│  ├─ architecture/
│  ├─ api/
│  ├─ deployment/
│  ├─ security/
│  ├─ data/
│  ├─ evals/
│  └─ ui/
├─ tests/
│  ├─ unit/
│  ├─ integration/
│  ├─ e2e/
│  └─ load/
└─ deliverables/
   ├─ phase-00/
   ├─ phase-01/
   ├─ phase-02/
   ├─ ...
   └─ final-release/
```

---

## 8) Product Modules

### A. Bid Strategy Optimizer
**Inputs**
- school
- GPA band
- practice interests
- city / office preference
- language ability
- extracurriculars
- desired bid count
- prior outcome data if available

**Outputs**
- ranked firm list
- reach / target / safer buckets
- confidence band
- explanation layer
- optional later counterfactual advice

**Model policy**
- start with rules + tabular ML
- do not use an LLM as the ranking engine
- add calibration before adding graph methods

### B. Firm Intelligence Briefs
**Inputs**
- firm slug
- office
- target practice area
- optional student profile context

**Outputs**
- 1-page brief
- recent signals
- differentiators
- practice notes
- talking points
- interview risks
- source freshness indicators

**System policy**
- normalize firm facts into tables first
- use retrieval on top
- provide grounded summaries

### C. Mock OCI Simulator
**Inputs**
- target firm
- target office
- text or later audio responses
- selected rubric
- time mode

**Outputs**
- transcript
- score breakdown
- weakness tags
- follow-up drill plan
- session history

**System policy**
- v1 must be a state machine
- text-first before audio
- store transcripts and scores for later analytics

### D. Cover Letter Co-pilot
**Inputs**
- resume
- firm
- office
- practice area
- prior draft or blank start

**Outputs**
- outline
- tailored draft
- rewrite pass
- anti-generic pass
- version history
- optional recruiter-signal alignment later

**System policy**
- outline first, draft second
- always store all versions
- maintain explainability around firm-specific tailoring

---

## 9) Data Model Roadmap

### Phase-early tables
- users
- sessions
- student_profiles
- student_preferences
- firms
- firm_offices
- firm_documents
- firm_news
- firm_facts
- bid_lists
- bid_list_items
- cover_letter_projects
- cover_letter_versions
- interview_sessions
- interview_turns
- interview_scores
- outcome_logs
- jobs
- embeddings
- eval_runs
- exports
- audit_logs

### Later-phase tables
- recruiter_signals
- student_memory_items
- calibration_models
- counterfactual_runs
- market_time_series
- graph_nodes
- graph_edges
- voice_metrics

---

## 10) API Surface (Initial)

```text
GET    /health
GET    /version

POST   /auth/register
POST   /auth/login
POST   /auth/logout
GET    /me
PATCH  /me/profile

GET    /firms
GET    /firms/{slug}
GET    /firms/{slug}/brief
POST   /firms/{slug}/refresh

POST   /bid-lists
GET    /bid-lists/{id}
POST   /bid-lists/{id}/score
POST   /bid-lists/{id}/log-outcome

POST   /cover-letters/projects
GET    /cover-letters/projects/{id}
POST   /cover-letters/projects/{id}/outline
POST   /cover-letters/projects/{id}/generate
POST   /cover-letters/projects/{id}/revise

POST   /interviews/sessions
GET    /interviews/sessions/{id}
POST   /interviews/sessions/{id}/message
POST   /interviews/sessions/{id}/finish

POST   /documents/upload
POST   /admin/reingest
GET    /admin/jobs
GET    /admin/ingestion-status

POST   /billing/checkout
POST   /billing/webhook
GET    /dashboard
```

---

## 11) UI / UX Requirements

The final app must look like a real premium legal-tech product.

### Public pages
- Home / landing
- Features
- Pricing
- About / trust / methodology
- FAQ
- Contact / waitlist / support
- Terms / privacy

### App pages
- Student onboarding
- Dashboard
- Firm browser
- Firm brief page
- Bid strategy workspace
- Mock interview workspace
- Cover letter workspace
- Settings
- Billing
- Admin / data operations

### Design requirements
- legal-tech premium look
- mobile-responsive
- strong typography hierarchy
- cards + tables + filters + search
- empty/loading/error states
- accessible forms
- polished onboarding funnel
- deployable visual quality from Phase 1 onward

---

## 12) Testing Requirements

Every phase must increase test coverage appropriately.

### Minimum
- unit tests for new business logic
- integration tests for all new API routes
- e2e smoke tests for critical UI flows
- regression tests for prompt outputs where relevant
- ranking evals for recommendation logic
- artifact generation tests for docx/zip flow

### Never mark a phase complete if
- CI is failing
- migrations are untested
- staging deploy is broken
- critical flows cannot be demonstrated

---

## 13) Security & Privacy Rules

1. No browser-side provider keys.
2. No secrets in repo history.
3. Use environment variables and secret managers supported by the chosen deployment target.
4. Log sensitive operations, but never log raw credentials.
5. Treat uploaded resumes and interview transcripts as sensitive data.
6. Minimize personal data in logs and analytics.
7. Include a deletion/export path for user content in later phases.
8. Add abuse controls for costly endpoints.
9. Review scraping legality and rate limits before implementation.

---

## 14) Research Gate — Mandatory Before Every Phase

Before starting each phase, do this exactly:

### Step A — Create research folders
Create:
```text
/deliverables/phase-XX/research/
```

### Step B — Research outputs
Produce:
- `research_memo.md`
- `decision_log.md`
- `risk_register.md`
- `sources.json`
- `cost_note.md`
- `security_note.md`

### Step C — Source priority
1. official product docs
2. official platform docs
3. primary technical references
4. only then secondary sources

### Step D — Required questions
For each phase, answer:
- What is the safest implementation pattern?
- What is the fastest implementation pattern?
- What is the cheapest GitHub Education-compatible pattern?
- What are the main lock-in risks?
- What are the main security risks?
- What is the smallest shippable version of the phase?
- What should be deferred to a later phase?

### Step E — Decision output
Choose one path and document:
- why chosen
- why rejected alternatives were rejected
- what assumptions remain uncertain

### Step F — Proceed automatically
After the research gate, proceed to implementation unless blocked by a real external dependency.

---

## 15) Per-Phase Artifact Rules

At the end of every phase, generate:

```text
/deliverables/phase-XX/
  phase-XX-report.docx
  phase-XX-package.zip
  summary.md
  changelog.md
  deploy-info.json
  screenshots/
  test-results/
  research/
  diffs/
  logs/
```

### DOCX report must include
- objective of phase
- research summary
- architecture decisions
- files created and modified
- migrations added
- endpoints added
- UI shipped
- tests added
- deployment steps completed
- screenshots
- blockers / risks
- next-phase recommendation

### ZIP package must include
- report docx
- summary markdown
- screenshots
- migration files
- relevant configs
- test results
- changelog
- deploy notes
- environment variable template additions

### Artifact generation policy
Use Python scripts in the repo to generate both the DOCX and ZIP automatically. Do not rely on manual packaging.

---

## 16) Phase Plan

### Phase 00 — Foundation, repo controls, artifact system
**Research**
- monorepo best practices
- Codespaces setup
- GitHub Actions structure
- artifact generation flow
- DigitalOcean deployment flow
- secret handling

**Build**
- repo scaffold
- AGENTS.md
- .codex config
- custom agents
- skills skeletons
- Docker Compose
- CI
- staging deploy shell
- artifact generator

**Exit criteria**
- local dev works in Codespaces
- CI passes
- blank app deploys to staging
- artifacts generate automatically

---

### Phase 01 — UX shell and app skeleton
**Research**
- Next.js App Router
- accessibility and responsive dashboards
- B2C/B2B SaaS onboarding
- auth/session architecture

**Build**
- polished landing page
- pricing page
- app shell
- auth shell
- dashboard shell
- onboarding flow
- admin shell
- design system
- common UI components

**Exit criteria**
- visually polished staging site
- app navigation works
- screenshots captured
- responsive on mobile/desktop

---

### Phase 02 — Data foundation and ingestion
**Research**
- scraping architecture
- idempotent ingestion
- chunking + embedding
- pgvector usage
- provenance and freshness tracking

**Build**
- firm schema
- document ingestion
- admin reingest tools
- scheduled jobs
- chunk + embed pipeline
- firm fact normalization
- job tracking and job logs

**Exit criteria**
- 10–20 seeded firms
- at least one automated ingestion path
- retrieval smoke tests pass
- admin can rerun jobs

---

### Phase 03 — Firm briefs and cover letter v1
**Research**
- RAG best practices
- grounded generation
- citation / source display patterns
- resume parsing strategy
- rewrite evaluation

**Build**
- firm brief endpoint + UI
- firm brief caching
- resume upload + parsing
- cover letter outline flow
- draft generation flow
- rewrite flow
- version history
- prompt eval harness

**Exit criteria**
- user can generate firm briefs
- user can generate and revise letters
- prompt eval outputs are reproducible

---

### Phase 04 — Bid optimizer v1
**Research**
- tabular ranking baselines
- feature engineering
- confidence labeling
- offline validation
- dataset constraints

**Build**
- feature store basics
- baseline rules model
- baseline gradient-boosted model
- scoring API
- explanation layer
- bid list UI
- outcome logging
- eval dataset

**Exit criteria**
- user gets ranked list + explanation
- confidence labels shown
- offline eval report saved

---

### Phase 05 — Mock OCI v1 + beta launch
**Research**
- interview state machines
- rubric scoring
- conversation persistence
- billing/paywall basics
- beta SaaS launch checklist

**Build**
- text-based interview state machine
- timers
- transcript persistence
- scoring rubric
- review dashboard
- Stripe checkout + entitlements
- admin analytics
- production deploy hardening

**Exit criteria**
- complete beta website live
- users can sign up, pay, and use core flows
- monitoring and alerts active

---

### Phase 06 — Personalization and memory
**Research**
- persistent memory retrieval
- longitudinal personalization
- privacy boundaries
- daily recommendation patterns

**Build**
- student memory store
- memory-aware recommendations
- daily prep planner
- dashboard personalization
- memory retrieval logs/auditability

**Exit criteria**
- personalized dashboard works
- memory retrieval is scoped and testable

---

### Phase 07 — Recruiter signals, calibration, counterfactuals
**Research**
- signal ingestion
- confidence calibration
- counterfactual UX
- temporal signal handling

**Build**
- recruiter/public signal jobs
- calibration layer
- confidence intervals
- counterfactual engine
- explanation cards
- signal dashboard widgets

**Exit criteria**
- recommendations show confidence bands
- counterfactual suggestions are visible
- temporal signals are versioned and reproducible

---

### Phase 08 — Runtime multi-agent orchestration
**Research**
- manager vs handoff patterns
- agent traces
- failure fallback
- evals for multi-agent improvement
- guardrails

**Build**
- minimal orchestrator
- only the runtime agents justified by evals
- traces
- guardrails
- fallback-to-single-agent path

**Exit criteria**
- multi-agent workflows measurably outperform single-agent baseline for selected tasks
- traces are stored
- failures degrade gracefully

---

### Phase 09 — Knowledge graph and voice
**Research**
- knowledge graph architecture
- graph feature serving
- speech analytics
- cost control

**Build**
- graph node/edge pipeline
- graph-aware queries
- voice upload/transcription/pacing/filler analysis
- advanced eval suites

**Exit criteria**
- graph and voice are optional, stable, and separately testable

---

## 17) Custom Codex Agent System

Create at least **30 custom Codex agents** under `.codex/agents/`.

### A. Program control
1. `program_manager`
2. `repo_planner`
3. `release_manager`

### B. Research
4. `official_docs_researcher`
5. `architecture_researcher`
6. `security_researcher`
7. `deployment_researcher`
8. `cost_researcher`
9. `ux_researcher`
10. `data_policy_researcher`
11. `model_researcher`
12. `evals_researcher`

### C. Build
13. `frontend_architect`
14. `ui_system_builder`
15. `backend_architect`
16. `api_engineer`
17. `data_engineer`
18. `scraper_engineer`
19. `rag_engineer`
20. `ml_scoring_engineer`
21. `interview_engineer`
22. `writing_engineer`
23. `auth_engineer`
24. `billing_engineer`
25. `devops_engineer`
26. `observability_engineer`
27. `artifact_engineer`

### D. Review
28. `qa_reviewer`
29. `security_reviewer`
30. `performance_reviewer`
31. `accessibility_reviewer`
32. `docs_reviewer`
33. `release_reviewer`

### Agent rules
- do not spawn all agents at once
- use waves of 4–6 max unless there is a strong reason otherwise
- research agents are read-only
- build agents must run tests before reporting done
- reviewers must comment with concrete pass/fail findings
- keep subagent depth low
- use a manager pattern, not chaotic peer delegation

---

## 18) Codex Config Requirements

Create `.codex/config.toml` and keep it project-scoped.

It must:
- define project defaults
- keep agent usage bounded
- include profiles if helpful
- document trusted-project assumptions
- avoid project settings that break local execution

Use project-local config because Codex supports `.codex/config.toml` in trusted projects.

---

## 19) Skills to Create

Create at least these skills under `.codex/skills/`:

1. `phase-research-gate`
2. `phase-report-export`
3. `monorepo-bootstrap`
4. `nextjs-ui-build`
5. `fastapi-endpoint-build`
6. `alembic-migration`
7. `scraper-pattern`
8. `rag-pipeline`
9. `ranking-evals`
10. `mock-interview-state-machine`
11. `stripe-billing-setup`
12. `deploy-digitalocean`
13. `deploy-azure-fallback`
14. `datadog-observability`
15. `artifact-docx-zip`
16. `security-review-checklist`
17. `staging-smoke-tests`
18. `release-cutover`

### Skill rules
- every skill must have `SKILL.md`
- use clear `name` and `description`
- descriptions must explicitly say when the skill should and should not trigger
- add scripts only when they provide repeatable value

---

## 20) AGENTS.md Requirements

The root `AGENTS.md` must define:

- mission
- product scope
- GitHub Education service policy
- stack policy
- source-of-truth files
- phase workflow
- research gate rule
- deliverable rule
- testing rule
- deployment rule
- no-browser-secrets rule
- runtime multi-agent restriction
- coding style
- branch/merge policy
- definition of done
- artifact generation rule
- how to proceed when uncertain

---

## 21) Branching, Release, and Deployment Policy

### Branches
- `main` = production
- `develop` = staging integration
- `phase/XX-*` = active phase branch
- feature branches under the phase branch when needed

### Release flow
1. complete phase work on phase branch
2. pass tests
3. deploy to staging
4. generate artifacts
5. merge into `develop`
6. validate staging
7. tag release candidate
8. merge to `main`
9. deploy production
10. archive phase package

### Required output after each phase
- tag
- release notes
- artifact package
- deploy-info.json

---

## 22) Data / Model / Evals Policy

1. Use structured ML for ranking before LLM ranking.
2. Use LLMs for drafting, summarization, conversational flows, and retrieval-backed writing.
3. Keep prompts version-controlled.
4. Store eval datasets.
5. Re-run evals after model or prompt changes.
6. Never silently swap a ranking method without updating the research and decision logs.
7. Recommendations must be explainable.
8. Confidence must be displayed carefully once introduced.

---

## 23) What Not to Build Too Early

Do not build these before their designated phase:
- graph neural network
- voice scoring
- burnout / wellness predictions
- full psychometric profiling
- RLHF pipeline
- broad LinkedIn-scale scraping operation
- runtime multi-agent orchestration
- advanced temporal intelligence layer

---

## 24) Definition of Done

A phase is complete only if:
- research memo exists
- code exists
- tests pass
- staging deploy succeeds
- production strategy is documented
- docx report is generated
- zip package is generated
- screenshots exist
- changelog is updated
- next-phase notes are written

The project is complete only if:
- the site is live
- the core student flows work end-to-end
- billing works
- admin tools work
- docs are sufficient for another engineer to operate the platform

---

## 25) Immediate Execution Order

Execute in this order unless blocked:

1. create repo scaffold
2. create `AGENTS.md`
3. create `.codex/config.toml`
4. create all custom agent stubs
5. create skill stubs
6. run Phase 00 research gate
7. implement Phase 00
8. generate Phase 00 docx + zip
9. continue phase by phase automatically

Do not skip artifact generation. Do not skip staging deployment. Do not jump to advanced intelligence layers before the earlier phases are stable.

---

## 26) Final Instruction

You are not writing a prototype.  
You are building a deployable, production-style legal-tech web platform under GitHub Education resource constraints, with phased research gates, Codex-specific workflow infrastructure, deliverable packaging, and a clear path from deployable v1 to intelligent moat features.

Start now.
