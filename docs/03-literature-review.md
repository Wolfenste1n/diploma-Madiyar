# 3. Literature review

## 3.1 Selection of sources

Sources were chosen around five themes that the project depends on: LLM agents and tool use, task-oriented dialogue with LLMs, reliability and security (hallucination, prompt injection, output formats), evaluation methods, and lead scoring. The review uses 18 sources: 13 scientific publications (12 from 2023 to 2025 and one foundational work from 2020) and 5 technical documents. Every scientific source has a DOI or arXiv identifier, and copies are stored in the repository ([papers folder](https://github.com/Wolfenste1n/diploma-Madiyar/tree/prob-period-1/papers)).

## 3.2 Structured analysis table

| # | Source (venue) | Year | What it shows | Limitation for this project | Identifier |
|---|---|---|---|---|---|
| 1 | Yao et al., ReAct (ICLR) | 2023 | Reasoning interleaved with tool calls | General benchmarks, not sales chats | [arXiv:2210.03629](https://arxiv.org/abs/2210.03629) |
| 2 | Schick et al., Toolformer (NeurIPS) | 2023 | Language models learn to call APIs | Training-based; the project uses prompts | [arXiv:2302.04761](https://arxiv.org/abs/2302.04761) |
| 3 | Wang et al., survey of LLM-based agents (Frontiers of Computer Science) | 2024 | Agent modules: memory, planning, action | Survey; no small-business guidance | [arXiv:2308.11432](https://arxiv.org/abs/2308.11432) |
| 4 | Gao et al., RAG survey (arXiv) | 2023 | Grounding reduces fabrication | Generic; a domain knowledge base is needed | [arXiv:2312.10997](https://arxiv.org/abs/2312.10997) |
| 5 | Hudeček, Dušek (SIGDIAL) | 2023 | LLMs are weak at slot tracking | Benchmark dialogues in English | [doi:10.18653/v1/2023.sigdial-1.21](https://doi.org/10.18653/v1/2023.sigdial-1.21) |
| 6 | Yao et al., tau-bench (arXiv) | 2024 | Judge the end state of tool use | Retail and airline domains | [arXiv:2406.12045](https://arxiv.org/abs/2406.12045) |
| 7 | Ji et al., hallucination survey (ACM Computing Surveys) | 2023 | Hallucination types and mitigations | Not specific to sales chats | [arXiv:2202.03629](https://arxiv.org/abs/2202.03629) |
| 8 | Zheng et al., LLM-as-a-Judge (NeurIPS D&B) | 2023 | LLM judges agree with humans | Biased; used only as a secondary scorer | [arXiv:2306.05685](https://arxiv.org/abs/2306.05685) |
| 9 | Greshake et al., indirect prompt injection (AISec) | 2023 | Untrusted text hijacks tools | Shows attacks; defenses are tested here | [arXiv:2302.12173](https://arxiv.org/abs/2302.12173) |
| 10 | Tam et al., format restrictions (EMNLP Industry) | 2024 | Strict output formats can hurt reasoning | Effect depends on the model; ablation planned | [arXiv:2408.02442](https://arxiv.org/abs/2408.02442) |
| 11 | González-Flores et al., B2B lead scoring (Frontiers in AI) | 2025 | Machine learning scores B2B leads | Structured data, not chats | [doi:10.3389/frai.2025.1554325](https://doi.org/10.3389/frai.2025.1554325) |
| 12 | Wu, Andreev, Benyoucef, lead scoring review (Information Technology and Management) | 2023 | Traditional vs predictive scoring; 44 studies | Review; no LLM agents | [doi:10.1007/s10799-023-00388-w](https://doi.org/10.1007/s10799-023-00388-w) |
| 13 | Lewis et al., RAG (NeurIPS), foundational | 2020 | Retrieval grounding for NLP | Pre-dates LLM agents | [arXiv:2005.11401](https://arxiv.org/abs/2005.11401) |

## 3.3 Synthesis

- **What approaches exist.** Tool-calling agents (sources 1 to 3), retrieval grounding (4, 13), explicit evaluation of agent behavior (6, 8) and lead scoring with machine learning on structured data (11, 12).
- **What is already known.** The agent loop is established; reliability is the open issue. LLMs are weak at exact slot tracking (5), hallucinate (7), can be hijacked through untrusted text (9) and can lose reasoning quality under strict output formats (10).
- **Limitations the project takes into account.** The design therefore uses an explicit state machine, schema validation, knowledge-base-only answers for facts, a tool whitelist, end-state evaluation of the CRM record (6) and human labels as the primary metric, with LLM judges only as a secondary scorer.

## 3.4 Gap

Lead scoring studies work with structured data and do not cover free-text messenger conversations; agent studies use general benchmarks. No evaluated pipeline turns messenger chats into validated CRM lead cards with human handoff for small businesses. This is the gap the project addresses.

## 3.5 Technical documentation

| # | Source | Link |
|---|---|---|
| 14 | HighLevel Support, How to set up a Conversation AI bot | [help.gohighlevel.com article](https://help.gohighlevel.com/support/solutions/articles/155000004401-how-to-set-up-a-conversation-ai-bot) |
| 15 | Meta, WhatsApp Business Platform, Cloud API | [developers.facebook.com](https://developers.facebook.com/docs/whatsapp/cloud-api) |
| 16 | Telegram, Bot API | [core.telegram.org](https://core.telegram.org/bots/api) |
| 17 | Bitrix24, REST API | [apidocs.bitrix24.com](https://apidocs.bitrix24.com) |
| 18 | OWASP, Top 10 for LLM Applications | [owasp.org](https://owasp.org/www-project-top-10-for-large-language-model-applications) |

## 3.6 Supporting materials

- Sources table with authors, venues, identifiers and links: [Diploma_sources.xlsx](https://github.com/Wolfenste1n/diploma-Madiyar/blob/prob-period-1/papers/Diploma_sources.xlsx)
- Copies of the papers (PDF) and a numbered index: [papers/](https://github.com/Wolfenste1n/diploma-Madiyar/tree/prob-period-1/papers)
