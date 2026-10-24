# LLM Agent for Processing and Qualifying Leads from a Messaging Platform with CRM Integration

- **EN:** Development of an LLM Agent for Processing and Qualifying Leads from a Messaging Platform with CRM Integration
- **RU:** Разработка LLM-агента для обработки и квалификации лидов из мессенджера с интеграцией в CRM-систему
- **KZ:** Мессенджер арқылы келіп түскен лидтерді өңдеу және саралау үшін CRM жүйесімен біріктірілген LLM-агентін әзірлеу

## Team and supervision

| Role | Name |
|---|---|
| Student (individual project) | Madiyar Kenzhebayev, group SE-2407, Astana IT University |
| Supervisor | Zhanna Bakirbaevna Sadirmekova, PhD, Associate Professor |

Topic status: approved by the supervisor; committee approval pending.

## Problem, users, outcomes

Leads arrive in Telegram and WhatsApp in free text; one manager cannot answer all of them in time and copies data into the CRM by hand. The project builds and evaluates an LLM agent that qualifies leads and writes validated lead cards to a CRM, with handoff to a human. Target users: customers, sales managers, and the operator (LeadUp agency). Pilot: Altay Santeh Opt, Astana.

Expected outcomes: a working MVP (Telegram, Bitrix24 adapter, handoff), an evaluation report against baselines, documentation and a reproducible setup.

Scope: Telegram, WhatsApp, Russian text, Bitrix24 adapter, human handoff, evaluation. Out of scope: Instagram, TikTok, voice, own CRM, fine-tuning.

## Current status

**Stage: probationary period 1 (analysis and design). No runnable code yet.** Version for the consolidated report: tag `prob-period-1`.

## Documentation (sections 1 to 11)

| Section | File |
|---|---|
| 1 Project proposal | [docs/01-project-proposal.md](docs/01-project-proposal.md) |
| 2 Evidence of relevance | [docs/02-evidence-of-relevance.md](docs/02-evidence-of-relevance.md) |
| 3 Literature review | [docs/03-literature-review.md](docs/03-literature-review.md) |
| 4 Existing system comparison | [docs/04-existing-system-comparison.md](docs/04-existing-system-comparison.md) |
| 5 Technology comparison | [docs/05-technology-comparison.md](docs/05-technology-comparison.md) |
| 6 Requirements specification | [docs/06-requirements-specification.md](docs/06-requirements-specification.md) |
| 7 Architecture and diagrams | [docs/07-architecture-and-diagrams.md](docs/07-architecture-and-diagrams.md) |
| 8 UX / prototype | [docs/08-ux-prototype.md](docs/08-ux-prototype.md) |
| 9 Verification and evaluation plan | [docs/09-verification-and-evaluation-plan.md](docs/09-verification-and-evaluation-plan.md) |
| 10 Project management and risks | [docs/10-project-management-and-risks.md](docs/10-project-management-and-risks.md) |
| 11 Supervisor feedback | [docs/11-supervisor-feedback.md](docs/11-supervisor-feedback.md) |

Consolidated report (PDF): [report/SE-2407_Kenzhebayev_ProbPeriod1.pdf](report/SE-2407_Kenzhebayev_ProbPeriod1.pdf)

## Repository structure

```
docs/        sections 1-11 and the task plan
diagrams/    editable Mermaid sources (*.mmd); PNG exports in diagrams/png/
prototype/   mockups of key scenarios
papers/      source papers (PDF), sources table, index
report/      consolidated report
src/         application code (empty at this stage)
tests/       automated tests (empty at this stage)
config/      configuration examples (placeholders only)
```

## Links

- YouTrack project DIP: https://madiyar-diploma.youtrack.cloud/dashboard?id=177-0
- Technologies (provisional): Python with FastAPI, PostgreSQL, Redis queue, hosted LLM API behind an interface, Telegram Bot API, WhatsApp Cloud API, Bitrix24 REST API.

## Working conventions

- Every work item is a YouTrack task `DIP-<n>` with owner, expected outcome, acceptance criteria and deadline.
- Branch `DIP-<n>-<slug>`; commit message `DIP-<n>: <what changed>`; changes go through a pull request that references the task.
- Secrets and personal data are never committed; use `config/.env.example` with placeholders.
