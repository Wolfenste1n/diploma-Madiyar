# 6. Requirements specification

Requirements were approved by the clients. Priorities follow MoSCoW. Numeric thresholds are initial targets and will be calibrated after the baseline is measured (section 9).

## 6.1 Functional requirements

<!-- widths: 8,31,9,34,18 -->
| ID | Requirement | Priority | Acceptance criterion | Verification |
|---|---|---|---|---|
| FR-01 | Receive and send text messages through the Telegram Bot API | Must | A message to the test bot is stored with channel, chat id and timestamp; the bot replies within NFR-01 | Integration test |
| FR-02 | Receive and send messages through the WhatsApp Cloud API | Must (iteration 2) | Round trip with a test number; only allowed message types (templates outside the 24-hour window) | Integration test, manual |
| FR-03 | Keep per-lead dialogue state and history across restarts | Must | After a restart the next message continues the same state | Integration test |
| FR-04 | Run a qualification dialogue that asks only for missing fields | Must | A field already provided is asked again in at most 5% of 20 scripted scenarios | Scenario test |
| FR-05 | Extract data into a typed lead schema and validate it | Must | 100% of stored leads pass validation; invalid output is retried, then flagged for a human | Schema test |
| FR-06 | Classify the lead as HOT, WARM or COLD with a short rationale | Must | Accuracy and macro-F1 against human labels are reported | Evaluation |
| FR-07 | Create or update the lead in the CRM through an adapter | Must | One CRM lead per chat with fields, summary and transcript link; no duplicates on repeated runs | Integration test (mock CRM, Bitrix24 sandbox) |
| FR-08 | Hand over to a human on triggers (explicit request, complaint, low confidence, out of scope, repeated misunderstanding) | Must | The manager is notified; the agent stops auto-replying until released; handoff recall is reported | Scenario test, evaluation |
| FR-09 | Answer FAQ from a knowledge base without inventing prices or stock | Should | Unsupported-claim rate on the FAQ set at or below the target | Evaluation |
| FR-10 | Operator edits fields, rules and the knowledge base without code changes | Should | A configuration change takes effect after reload | Manual test |
| FR-11 | Log every agent decision and report metrics | Should | Each dialogue has a trace; a script prints the metrics | Inspection |
| FR-12 | Send a follow-up if the lead is silent | Could | One reminder after a configured delay, only if channel rules allow | Manual test |
| FR-13 | Accept a photo as a hint | Could | The photo description is added to the lead card and marked unverified | Manual test |
| FR-14 | Instagram and TikTok channels | Won't (this release) | Documented as future work | None |

## 6.2 Non-functional requirements

<!-- widths: 9,18,10,43,20 -->
| ID | Area | Priority | Acceptance criterion | Verification |
|---|---|---|---|---|
| NFR-01 | Latency | Must | p95 first reply within 10 s (initial target) | Test run |
| NFR-02 | Reliability | Must | No lost messages; no duplicate replies on replay | Fault test |
| NFR-03 | Secrets | Must | No secrets in the repository; only placeholder examples | Inspection |
| NFR-04 | Privacy | Must | Evaluation data is anonymized; retention is configurable | Inspection |
| NFR-05 | Safety | Must | Only whitelisted tools; no destructive CRM tools; zero successful injection probes | Probe set |
| NFR-06 | Language | Must / Should | Russian required; Kazakh and English should | Scenario test |
| NFR-07 | Cost | Should | Cost per dialogue is reported | Evaluation |
| NFR-08 | Maintainability | Should | Channel, LLM and CRM are replaceable through interfaces; at least 70% line coverage of core logic (initial target) | Coverage report |

## 6.3 Lead schema (draft)

`name`, `phone`, `channel`, `intent` (buy, price, availability, consultation, other), `product_category`, `product_details` (sizes, connection type, quantity), `project_type` (apartment, house, commercial), `urgency` (today, this week, planning), `fulfilment` (delivery, pickup), `city`, `budget` (optional), `qualification` (HOT, WARM, COLD), `confidence`, `missing_fields[]`, `handoff_required`, `summary`.

## 6.4 Verifiability

All 14 mandatory requirements (8 functional and 6 non-functional) have a measurable criterion and a named verification method, so the fulfilment of each can be checked.
