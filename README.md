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

## Problem

Small businesses receive leads through messengers (Telegram, WhatsApp). One manager cannot answer every inbound message quickly, so leads wait for a reply, arrive with incomplete data, or never reach the CRM. Rule-based chatbots cover only fixed scripts and fail on free-form questions.

Evidence and its status (verified / author experience / assumption): [docs/02-evidence.md](docs/02-evidence.md).

## Target users

1. **Lead / customer** writing to a business in Telegram or WhatsApp.
2. **Sales manager** who receives qualified leads and handoffs.
3. **Business owner / operator** (LeadUp agency) who configures the qualification rules and monitors quality metrics.

Pilot domain: plumbing and heating supplies (Altay Santeh Opt, Astana).

## Aim

Design, implement and evaluate an LLM-based agent that talks to an inbound lead, collects the data needed for qualification, classifies the lead (HOT / WARM / COLD), and writes a complete, structured lead card to a CRM, handing over to a human when needed.

## Objectives

1. Collect evidence about the process and requirements (client and user discussions).
2. Review literature and existing systems; justify technology choices.
3. Specify requirements with acceptance criteria; design the architecture.
4. Implement the MVP: Telegram channel, agent core, CRM adapter (Bitrix24 + mock), human handoff.
5. Add the WhatsApp channel (Cloud API).
6. Evaluate against baselines on at least 100 labeled dialogues and report metrics.

## Expected outcomes

A working MVP, an evaluation report with metrics against baselines, documentation, and a reproducible setup.

## Scope

| In scope | Out of scope (this release) | Stretch |
|---|---|---|
| Telegram, WhatsApp, text dialogues (Russian first), one CRM adapter (Bitrix24), human handoff, evaluation | Instagram, TikTok, voice, building an own CRM, fine-tuning foundation models | Photo hints, follow-up reminders, Kazakh dialogues |



## Selected technologies (provisional, see docs/05)

Python + FastAPI, PostgreSQL, Redis job queue, hosted LLM API behind an abstraction layer, Telegram Bot API, WhatsApp Cloud API, Bitrix24 REST API.


