# OCI-AI Scaffold

This repository is scaffolded from `codex_oci_architecture_spec_v2.md` Section 7.

## Top-level modules
- `.github/` automation workflows and issue templates
- `.codex/` local agent/skill/prompt/template assets
- `apps/` runtime applications (`web`, `api`, `worker`)
- `packages/` shared libraries and configuration
- `data-pipelines/` ingestion and feature-building jobs
- `infra/` deployment and operational assets
- `docs/` product and engineering documentation
- `tests/` test suites
- `deliverables/` phase-by-phase artifacts

## Scaffolded structure

```text
.github/workflows
.github/ISSUE_TEMPLATE
.codex/agents
.codex/skills
.codex/prompts
.codex/templates
apps/web
apps/api
apps/worker
packages/ui
packages/prompts
packages/schemas
packages/evals
packages/config
packages/client
data-pipelines/nalp
data-pipelines/firms
data-pipelines/schools
data-pipelines/public-signals
data-pipelines/feature-builders
infra/docker
infra/deploy
infra/migrations
infra/monitoring
infra/seed
infra/scripts
docs/architecture
docs/api
docs/deployment
docs/security
docs/data
docs/evals
docs/ui
tests/unit
tests/integration
tests/e2e
tests/load
deliverables/phase-00
deliverables/phase-01
deliverables/phase-02
deliverables/final-release
```
