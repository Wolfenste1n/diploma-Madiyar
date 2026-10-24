# 9. Verification and evaluation plan

## 9.1 Research questions

1. How accurately does the agent extract lead fields from free-text dialogues?
2. How well does it classify HOT, WARM and COLD compared with a human manager?
3. Does it hand over to a human when it should and avoid inventing facts?
4. Is it faster than the current process, and what does it cost?

## 9.2 Test data

| Set | Content | Size (target) | Source |
|---|---|---|---|
| T1 | Anonymized real dialogues | as available, at least 30 | Altay Santeh Opt, with written consent; names and phones removed |
| T2 | Synthetic dialogues for rare cases | at least 70 | Generated and reviewed by the author |
| T3 | FAQ and no-invention probes (price, stock, discount questions) | 30 | Author, based on the discussions |
| T4 | Prompt-injection probes | 20 | Author, informed by the OWASP LLM Top 10 |

Labels: two annotators (the author and, if possible, the client's manager) label fields, class and handoff; disagreement is reported as Cohen's kappa. The test set is frozen before prompt tuning; tuning uses a separate development split.

## 9.3 Outcome metrics

| Metric | Definition | Initial target |
|---|---|---|
| Field F1 | Per-field precision and recall against gold labels | 0.85 or higher |
| Qualification accuracy and macro-F1 | Agent class against human class | accuracy 0.80 or higher |
| Handoff recall and precision | Correct handoffs among required and among performed | recall 0.90 or higher |
| Unsupported-claim rate | Share of answers with price, stock or terms absent from the knowledge base | 2% or lower |
| Injection success rate | Probes that cause an unauthorized tool call or policy break | 0% |
| Task success (end state) | The CRM record equals the expected record | reported |
| Latency and cost | p95 first reply; cost per completed dialogue | under 10 s |

Targets are hypotheses and will be calibrated with the supervisor after the baseline run.

## 9.4 Baselines and ablations

| ID | Baseline | Purpose |
|---|---|---|
| B1 | Rule-based decision-tree bot with fixed questions | Shows the value of free-text understanding |
| B2 | Make / n8n with a single LLM prompt, no validation or state machine | Shows the value of the engineering layers |
| B3 | Human manager (reply times from real chat timestamps; labels as reference) | Comparison with the real process |
| A1 | Full system without schema validation | Ablation |
| A2 | Free-form against constrained output format | Ablation (literature source 10) |

## 9.5 Measurement conditions and test levels

- Fixed prompts and model version per run; temperature fixed; three runs per configuration; results as mean and range.
- Test levels: unit (parsers, schema, state machine), integration (webhook to CRM; mock CRM and a Bitrix24 sandbox), end-to-end scripted dialogues, and the evaluation harness.

## 9.6 How the aim will be demonstrated

The aim is demonstrated by metrics measured on labeled dialogues and compared with the three baselines. Plan: by pre-defense 1, the protocol (this section); by pre-defense 2, baselines B1 and B2 measured and the MVP evaluated on T1 and T2; at the final defense, full results, ablations and error analysis.
