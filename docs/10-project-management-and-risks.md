# 10. Project management and risks

## 10.1 Repository and tracker

- Git repository: [github.com/Wolfenste1n/diploma-Madiyar](https://github.com/Wolfenste1n/diploma-Madiyar), version for this report: tag [prob-period-1](https://github.com/Wolfenste1n/diploma-Madiyar/tree/prob-period-1).
- YouTrack project DIP: [madiyar-diploma.youtrack.cloud](https://madiyar-diploma.youtrack.cloud/dashboard?id=177-0).
- Conventions: branch `DIP-<n>-<slug>`, commit message `DIP-<n>: <what changed>`, one pull request per task that references the YouTrack task and states how the work was checked; the supervisor reviews significant changes at checkpoints. Tags: `prob-period-1`, then one tag per later submission.

## 10.2 Responsibilities

| Who | Responsibility |
|---|---|
| Student (Madiyar Kenzhebayev) | Analysis, design, code, evaluation, documentation, all YouTrack tasks |
| Supervisor (Zhanna B. Sadirmekova) | Reviews key deliverables at agreed checkpoints |
| Experts and client | Discussions, approval of requirements, anonymized dialogues |

## 10.3 Task plan (YouTrack project DIP)

<!-- widths: 8,46,10,12,12,12 -->
| ID | Task | Priority | Due date | Assignee | State |
|---|---|---|---|---|---|
| DIP-1 | Create repository and README | Critical | 2026-10-13 | Student | see YouTrack |
| DIP-2 | Set up YouTrack and create tasks | Critical | 2026-10-13 | Student | see YouTrack |
| DIP-3 | Project proposal | Major | 2026-10-13 | Student | see YouTrack |
| DIP-4 | Evidence: expert discussions and client agreement | Critical | 2026-10-20 | Student | see YouTrack |
| DIP-5 | Literature review and source papers | Major | 2026-10-22 | Student | see YouTrack |
| DIP-6 | Existing systems comparison | Major | 2026-10-22 | Student | see YouTrack |
| DIP-7 | Technology comparison | Major | 2026-10-20 | Student | see YouTrack |
| DIP-8 | Requirements specification | Critical | 2026-10-20 | Student | see YouTrack |
| DIP-9 | Architecture diagrams | Major | 2026-10-22 | Student | see YouTrack |
| DIP-10 | Prototype | Major | 2026-10-22 | Student | see YouTrack |
| DIP-11 | Verification and evaluation plan | Major | 2026-10-22 | Student | see YouTrack |
| DIP-12 | Process supervisor feedback | Normal | 2026-10-24 | Student | see YouTrack |
| DIP-13 | Telegram gateway skeleton | Major | 2026-11-07 | Student | see YouTrack |
| DIP-14 | Agent core: state machine and schema validation | Critical | 2026-11-21 | Student | see YouTrack |
| DIP-15 | CRM adapter interface, mock CRM, Bitrix24 adapter | Major | 2026-11-28 | Student | see YouTrack |
| DIP-16 | Dataset and labeling protocol | Major | 2026-12-05 | Student | see YouTrack |
| DIP-17 | WhatsApp channel | Normal | 2026-12-12 | Student | see YouTrack |
| DIP-18 | Baselines and evaluation harness | Major | 2026-12-19 | Student | see YouTrack |

The current state of every task, with expected outcome, acceptance criteria and links to commits, is kept in YouTrack; the plan is also stored as [DIP_task_plan.pdf](https://github.com/Wolfenste1n/diploma-Madiyar/blob/prob-period-1/docs/DIP_task_plan.pdf).

## 10.4 Milestones

| Milestone | Date | Content |
|---|---|---|
| Pre-defense 1 (probationary period 1) | 24 October 2026 | Analysis, requirements, architecture, prototype, evaluation plan, repository and tracker |
| MVP core | November 2026 | Telegram gateway, agent core, mock CRM, Bitrix24 adapter |
| Extensions | December 2026 | WhatsApp channel, injection tests |
| Pre-defense 2 | May 2027 | End-to-end MVP, baselines measured |
| Final defense | June 2027 | Full evaluation, ablations, documentation |

## 10.5 Risks

<!-- widths: 6,24,10,10,38,12 -->
| ID | Risk | Likelihood | Impact | Mitigation | Level |
|---|---|---|---|---|---|
| R1 | The model invents prices or stock | Medium | High | Answers only from the knowledge base; handoff for quotes; unsupported-claim metric | High |
| R2 | Prompt injection through customer text | Medium | High | Tool whitelist, no destructive CRM tools, output validation, probe set | High |
| R3 | WhatsApp onboarding or template rules delay the channel | High | Medium | Telegram first; WhatsApp in the second iteration; aggregator as a fallback | Medium |
| R4 | Not enough real dialogues for evaluation | Medium | High | Synthetic set reviewed by the author; limits stated honestly | Medium |
| R5 | Personal data in dialogues | Medium | High | Anonymize before storage; written consent; configurable retention | High |
| R6 | Client or experts unavailable | Medium | Medium | Use the second domain contact; document the limitation | Medium |
| R7 | Scope too large for one student | Medium | High | MVP first; Instagram, photos, Kazakh stay stretch | Medium |
| R8 | LLM cost or latency above target | Low | Medium | Shorter prompts, caching, model choice behind an interface | Low |
| R9 | Dependence on one vendor API | Medium | Medium | LLM and CRM interfaces | Medium |

## 10.6 Dependencies

Bitrix24 plan with REST API and webhooks; WhatsApp Business account; LLM API access and budget; written consent of the client for dialogue data; supervisor availability for checkpoints.

## 10.7 Next steps

Finish the remaining expert discussions and collect the client metrics; start the Telegram gateway and the agent core (DIP-13, DIP-14); keep every commit linked to a YouTrack task.
