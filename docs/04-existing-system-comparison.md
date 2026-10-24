# 4. Existing system comparison

## 4.1 Systems and criteria

Four existing approaches were compared against this project on eight criteria. The set of systems covers an all-in-one CRM platform, a CRM marketplace app, an independent AI-agent service and a do-it-yourself pipeline, which are the options a small business realistically has.

- **HighLevel Conversation AI:** a bot built into a CRM and marketing platform.
- **Bitrix24 with an AI app from the marketplace:** messaging channels plus a third-party AI app.
- **Moon AI:** a third-party AI-agent service connected to Bitrix24 and other CRMs.
- **Make / n8n with an LLM:** a do-it-yourself pipeline (the approach the author used before).

<!-- widths: 14,17,16,17,17,19 -->
| Criterion | HighLevel Conversation AI | Bitrix24 + AI app | Moon AI | Make / n8n + LLM | This project |
|---|---|---|---|---|---|
| Channels | WhatsApp, Instagram, SMS, chat | Telegram, WhatsApp, chat | WhatsApp, Telegram, Instagram | Any, built by hand | Telegram, WhatsApp |
| CRM integration | Native (same platform) | Writes Bitrix24 fields | Lead and deal (vendor claim) | Via API modules | Bitrix24 adapter and mock |
| Structured fields, validation | Not confirmed | Fields, validation not stated | Filled card (vendor claim) | Custom, none by default | Typed schema, validated |
| Human handoff | Message limits, modes | To a live manager (listing) | Not confirmed | Custom | Explicit triggers |
| Published quality method | Not found | Not found | Not found | None | Metrics against baselines |
| Control of data and prompts | Closed platform | Closed app | Closed service | Medium | Full, own server |
| Pricing model | Usage-based | License and message units | Subscription and tokens | Platform and API | Tokens and own server |
| Languages | Not confirmed | Not confirmed | RU, KZ, EN (vendor claim) | Depends on the LLM | Russian first |
| Evidence source | Help center (official) | Marketplace listings | Product pages (vendor claims) | Author experience | Planned, measured |

## 4.2 Evidence and its limits

- HighLevel: official help article, [How to set up a Conversation AI bot](https://help.gohighlevel.com/support/solutions/articles/155000004401-how-to-set-up-a-conversation-ai-bot).
- Bitrix24: marketplace listings of AI apps (vendor descriptions).
- Moon AI: product pages (vendor claims, not independently verified).
- Make / n8n: the author's own experience with such pipelines.
- "Not confirmed" and "Not found" mean that the reviewed material does not state the feature; they do not prove that it is absent.

## 4.3 Findings: why a new solution is needed

1. The function itself (qualify a lead and write it to a CRM) is already offered commercially, so the problem is real.
2. None of the reviewed products publishes a method for measuring quality (accuracy of qualification, share of invented facts, correctness of handoff); buyers have to trust claims.
3. Closed platforms limit control over prompts and data; a do-it-yourself pipeline gives control but has no validation or test framework.
4. This project adds a typed lead schema with validation, explicit handoff rules, a replaceable channel, LLM and CRM, and a reproducible evaluation against baselines.
