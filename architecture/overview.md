# Architecture Overview

Paperclip Agentic Ecommerce is a founder-controlled operating system for a lean DTC brand.

It borrows a useful pattern from strong agent submissions: make the repo look like the actual operating system, not merely a product idea. The architecture therefore documents agents, gates, workflows, skills, model routing, and Stripe actions as first-class pieces.

## System flow

```text
Squish business context
  + founder growth goal
  + investor-plan constraints
        |
        v
Cleo / Hermes Orchestrator
        |
        +--> Strategy / creator / funnel agents
        +--> Unit economics agent
        +--> Compliance agent
        +--> Supplier / ops agent
        +--> Stripe ops agent
        +--> Nemotron review layer
        |
        v
Founder operating packet
        |
        +--> approved local tasks
        +--> approval-gated Stripe actions
        +--> founder decision queue
        +--> GitHub/vault documentation
```

## Core principle

Paperclip should never be “agent as vibes.” Every recommendation must connect to one of four operating realities:

1. Customer acquisition.
2. Unit economics.
3. Compliance / risk.
4. Payment / provisioning / operational execution.

## Runtime layers

| Layer | Tooling | Purpose |
|---|---|---|
| Founder authority | Alexa | Taste, budget, approvals, strategic direction |
| Orchestration | Hermes Agent / Cleo | Skills, tools, memory, delegation, verification |
| Control plane | Paperclip | Agent structure, authority boundaries, budgets, heartbeat concept |
| Payment/provisioning | Stripe skills | Earn/spend/provision with approval ledgers |
| Reasoning review | Nemotron 3 Ultra | High-context viability and risk review |
| Business corpus | Vault + repo | Durable docs and operating artifacts |

## Data classes

| Data class | Examples | Routing |
|---|---|---|
| Public | Docs, public market sources, GitHub repo | Safe for cloud/model context |
| Business internal | Unit economics, launch plans, operating docs | Safe when sanitized; avoid private vendors |
| Sensitive commercial | Supplier quotes, private negotiations | Local/vault only unless approved |
| Financial credential | Stripe/API secrets, payment credentials | Never in prompts or repo |
| Customer private | PII, order data, payment identifiers | Local/tool-only, approval required |

## Why this matters for the hackathon

The brief asks for agents that can earn, spend, and run real operations. This architecture shows:

- how Paperclip earns by building acquisition workflows and offer economics,
- how it spends through approval-gated Stripe skills,
- how it runs operations through repeatable agent workflows and durable artifacts.
