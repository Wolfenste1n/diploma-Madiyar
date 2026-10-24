# 5. Technology comparison

## 5.1 Key technology decisions

Each decision lists the alternatives that were considered, the choice and the requirement that justifies it. Choices are provisional until the evaluation (section 9) measures quality and cost.

<!-- widths: 14,29,19,38 -->
| Decision | Alternatives considered | Chosen | Justification (requirements) |
|---|---|---|---|
| LLM access | Hosted API; open-weight model on own GPU; hybrid | Hosted API behind an interface | Best Russian quality for the MVP; replaceable (NFR-08); an open-weight model is compared in the evaluation |
| Orchestration | Own state machine; LangGraph; Make / n8n | Own state machine | The qualification process is bounded with explicit states; deterministic and testable (FR-04, FR-05) |
| Server platform | Python with FastAPI; Node.js | Python with FastAPI | LLM and evaluation ecosystem; typed schemas |
| Data storage | PostgreSQL; MongoDB; SQLite | PostgreSQL | Transactions for state, logs and the knowledge base in one database |
| WhatsApp access | Cloud API; aggregator; unofficial library | Cloud API (official) | Compliance with platform rules; unofficial libraries risk account bans |
| CRM | Bitrix24; amoCRM / Kommo; own CRM | Bitrix24 through an adapter | Part of the LeadUp stack; documented REST API; an own CRM is outside the aim |
| Component interaction | Webhooks with a queue; message broker; synchronous calls | Webhooks with a Redis queue | Fast webhook reply and no lost messages (NFR-01, NFR-02) |

Telegram uses the official Bot API.

## 5.2 Conclusion on technologies

Every choice is justified by a requirement and is replaceable behind an interface (LLM client, channel adapters, CRM adapter), so the contribution stays in the agent logic and its evaluation. Open questions: whether an open-weight model is competitive in Russian and Kazakh (measured in the evaluation) and whether fine-tuning is needed (only if the supervisor requires it).
