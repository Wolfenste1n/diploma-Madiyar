# 1. Project proposal

**Project title.** Development of an LLM Agent for Processing and Qualifying Leads from a Messaging Platform with CRM Integration

- Russian: Разработка LLM-агента для обработки и квалификации лидов из мессенджера с интеграцией в CRM-систему
- Kazakh: Мессенджер арқылы келіп түскен лидтерді өңдеу және саралау үшін CRM жүйесімен біріктірілген LLM-агентін әзірлеу

**Team.** Individual project. Student: Madiyar Kenzhebayev, group SE-2407, Astana IT University (AITU).

**Supervisor.** Zhanna B. Sadirmekova, PhD, Associate Professor.

**Topic status.** Approved by the supervisor; committee approval pending.

## 1.1 Problem statement

Small businesses receive leads through messengers (Telegram, WhatsApp) in free text and at any hour. A manager reads each message, asks follow-up questions (what product, what size, how urgent, delivery or pickup) and copies the result into a CRM by hand. When the number of messages exceeds the manager's capacity, leads wait for a reply and CRM records are incomplete or missing. Rule-based chatbots cover only fixed scripts and fail on free-form questions. Commercial AI agents exist, but none of the reviewed products publishes a method for measuring the quality of lead qualification (section 4).

## 1.2 Target users

| User | Need | Interaction with the system |
|---|---|---|
| Customer (lead) | A fast, relevant answer and a clear next step | Writes in Telegram or WhatsApp |
| Sales manager | Complete, prioritized lead cards; a handoff when a human is required | Works in the CRM (Bitrix24) |
| Operator (LeadUp agency) | Control of questions, rules and quality | Configures rules and reads metrics |

Pilot domain: plumbing and heating supplies, Altay Santeh Opt (Astana).

## 1.3 Aim

Build and evaluate an LLM agent that qualifies leads from messengers and writes validated lead cards to a CRM, handing over to a human when needed.

## 1.4 Objectives

1. Collect evidence about the process and requirements from the client and domain experts.
2. Review the literature and existing systems; justify technology choices.
3. Specify requirements with acceptance criteria; design the architecture.
4. Implement an MVP: Telegram channel, agent core, CRM adapter (Bitrix24 and a mock CRM), human handoff.
5. Add the WhatsApp channel (Cloud API).
6. Evaluate the agent against baselines on at least 100 labeled dialogues and report the metrics.

## 1.5 Expected outcomes

- A working MVP (Telegram, Bitrix24 adapter, handoff).
- An evaluation report with metrics compared with baselines.
- Documentation and a reproducible setup (this repository).

## 1.6 Project scope

| In scope | Out of scope (this release) | Stretch goals |
|---|---|---|
| Telegram and WhatsApp, text dialogues (Russian first), one CRM adapter (Bitrix24), human handoff, evaluation | Instagram, TikTok, voice, building an own CRM, fine-tuning foundation models | Photo hints, follow-up reminders, Kazakh dialogues |

## 1.7 Engineering complexity and realism of the scope

The engineering complexity lies in stateful dialogue management (an explicit state machine around the LLM), schema-constrained extraction with validation, tool use against a CRM through an adapter, guardrails against hallucination and prompt injection, asynchronous webhook processing and an evaluation harness with baselines. The scope is realistic for one student because the work is MVP-first: one pilot business, one CRM, one channel first (Telegram), and the remaining channels and features are separated as later iterations or stretch goals.
