# 🛍️ Paperclip Agentic Ecommerce

**An agentic ecommerce operating layer for Squish — a real pre-launch skincare brand. Built with Hermes Agent, Paperclip multi-agent orchestration, Stripe payment/provisioning gates, and NVIDIA Nemotron 3 Ultra as an operations review layer.**

> 🏆 Submitted to the [Hermes Agent Accelerated Business Hackathon](https://x.com/NousResearch/status/2066921443548348436) — presented by **@NVIDIAAI × @stripe × @NousResearch**
>
> **Public repository notice:** Paperclip Agentic Ecommerce is based on a real, active Squish business plan. The public repo contains sanitized strategy, architecture, sample workflows, and demo artifacts. Private supplier conversations, credentials, account details, live customer data, and unpublished operating records are intentionally excluded.
>
> **Project status note:** Squish was already being built as an agentic ecommerce skincare company before the hackathon. The hackathon aligned with the actual operating model we were designing: one founder supported by specialised AI agents for commerce, growth, compliance, supplier ops, and reporting.

## 🎥 Demo

**Watch:** [demo link pending]

## ✨ The thesis

Most ecommerce founders do not need “an AI that writes captions.” They need an operator that can help the business **earn, spend, and run** without losing control.

Paperclip turns a founder’s ecommerce goal into a governed operating workflow:

```text
Founder growth goal
  → campaign strategy
  → offer economics
  → compliance-safe messaging
  → creator/acquisition workflow
  → Stripe-governed payment/provisioning plan
  → approval ledger
  → founder-ready execution packet
```

## 🧴 Why Squish?

Squish is launching with premium visible hydrocolloid pimple patches: cute enough to wear publicly, credible enough to repurchase.

The investor-plan foundation:

- First SKU: 36–40 count visible hydrocolloid patches.
- Target price: $16 single pack.
- Bundle-led AOV target: $28–36.
- CAC target: $14–18 blended early.
- Claim lane: absorb fluid, protect from picking, support an ideal healing environment, surface whiteheads.
- GTM: Shopify → creator/social discovery → product page → bundle → post-purchase education → replenishment/review loop.

This is not a fake brand wrapped around a hackathon. Squish already needs the operating layer Paperclip describes.

## 🚨 The ecommerce problem

Early ecommerce brands fail in the messy middle:

- Supplier samples and cost assumptions live in scattered notes.
- Creative campaigns ignore unit economics.
- Founder taste gets diluted by generic automation.
- Skincare copy drifts into risky medical claims.
- Payments, SaaS, tools, and API spend happen without a clean audit trail.
- Investors cannot tell whether “AI operations” actually reduces fixed cost.

Paperclip addresses that by making every operating move structured, reviewable, and approval-gated.

## 🧠 What Paperclip does

| Capability | What it does |
|---|---|
| 🎯 **Brief intake** | Converts a founder growth goal into structured ecommerce workstreams |
| 💸 **Offer economics** | Checks price, AOV, COGS, fulfillment, processing fees, CAC, and LTV risk |
| 🧴 **Skincare compliance** | Keeps messaging cosmetic-safe and avoids medical acne-treatment claims |
| 👩‍🎤 **Creator acquisition** | Builds creator/affiliate campaign plans with FTC disclosure reminders |
| 🔵 **Stripe gates** | Queues purchases, provisioning, API usage, and checkout actions with approval records |
| 🟢 **Hermes skills** | Uses persistent skills/memory/filesystem workflows rather than one-off prompts |
| 🧠 **Nemotron review** | Stress-tests operating plans, payment risk, and viability before execution |
| 📊 **Founder packet** | Produces reusable artifacts: funnel, offer, tasks, risks, approval ledger |

## 🏗️ How it uses the sponsor stack

### 🟢 Hermes Agent — core runtime

Hermes Agent is the shell that makes the system operational:

- persistent project memory,
- reusable skills,
- filesystem artifacts,
- web/terminal/browser tools,
- approval-aware execution,
- scheduled workflows,
- model/provider routing.

### 🤖 Paperclip — multi-agent operating structure

Paperclip defines the company-like team structure:

| Agent | Role | Authority |
|---|---|---|
| **Cleo** | Founder-side orchestrator / brand operator | Delegates, synthesizes, escalates |
| **Mira** | Ecommerce strategist | Offer, funnel, audience, channel plan |
| **Ledger** | Unit economics analyst | CAC/AOV/COGS/LTV viability |
| **Vera** | Claims + FTC compliance | Cosmetic-safe copy and disclosure checks |
| **Atlas** | Supplier + operations tracker | Samples, vendors, QA docs, fulfillment dependencies |
| **Piper** | Creator acquisition operator | Seeding, affiliate, content handoffs |
| **Nova** | Stripe ops agent | Spend/provisioning/payment plan + approval ledger |
| **Nemo** | Nemotron review layer | Long-context operating review and risk critique |

Specialists do not act with unlimited authority. They report up to Cleo, and sensitive actions route to Alexa.

### 🟡 NVIDIA — Nemotron 3 Ultra

Nemotron 3 Ultra is positioned as the high-capacity operations reviewer for:

- ecommerce workflow viability,
- long-context business plan review,
- payment/provisioning risk checks,
- compliance and policy consistency,
- sponsor-demo presentation critique.

Nemotron does **not** hold payment credentials. It receives review packets, not secrets.

### 🔵 Stripe — earn + spend + provision

Paperclip incorporates the Hermes Stripe skills as the commerce action layer:

| Skill | Paperclip use |
|---|---|
| `stripe-projects` | Provision dev SaaS/infrastructure for campaign tracking, dashboards, databases, analytics |
| `stripe-link-cli` | Approval-gated operational purchases such as tools, samples, research resources |
| `mpp-agent` | Budget-capped pay-per-call APIs for enrichment, validation, or ecommerce intelligence |

Every financial action gets:

- business reason,
- estimated cost,
- spend cap,
- environment,
- approving human,
- verification command,
- audit record.

## 🧭 Architecture

```text
┌─────────────────────────────────────────────────────────────────┐
│                  ALEXA / FOUNDER AUTHORITY                       │
│          taste · approvals · budget · final judgment             │
└───────────────────────────────┬─────────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────────┐
│                      CLEO / HERMES ORCHESTRATOR                  │
│     skills · memory · files · tools · delegation · verification  │
└──────────────┬───────────────┬───────────────┬──────────────────┘
               │               │               │
     ┌─────────▼──────┐ ┌──────▼──────┐ ┌─────▼────────┐
     │ Strategy Team  │ │ Ops Team    │ │ Compliance   │
     │ Mira + Piper   │ │ Atlas+Ledger│ │ Vera         │
     └─────────┬──────┘ └──────┬──────┘ └─────┬────────┘
               │               │              │
               └───────────────┼──────────────┘
                               │
                 ┌─────────────▼─────────────┐
                 │ Operating Packet           │
                 │ offer · funnel · economics │
                 │ claims · tasks · risks     │
                 └─────────────┬─────────────┘
                               │
         ┌─────────────────────┼─────────────────────┐
         ▼                     ▼                     ▼
┌─────────────────┐   ┌──────────────────┐   ┌──────────────────┐
│ Stripe Ops      │   │ Nemotron Review  │   │ GitHub / Docs    │
│ approval ledger │   │ viability + risk │   │ public artifact  │
└─────────────────┘   └──────────────────┘   └──────────────────┘
```

See [`architecture/overview.md`](architecture/overview.md) and [`docs/TRD.md`](docs/TRD.md).

## 🔐 Approval gates

Paperclip uses a four-tier action policy:

| Tier | Action type | Example |
|---|---|---|
| **Tier 0 — Silent allowed** | Local reads/writes, drafts, analysis | Generate operating packet |
| **Tier 1 — Visible confirmation** | Low-risk external lookup | Read public documentation |
| **Tier 2 — Explicit approval** | Outreach, public posting, provisioning, purchases | Create Stripe service, buy tool, post campaign |
| **Tier 3 — Launch-forbidden until configured** | Live customer charges, production payments, credential changes | Charge customer, upgrade paid provider |

Cleo prepares. Alexa decides.

## 📦 Repository map

```text
.
├── README.md
├── SECURITY.md
├── docs/
│   ├── BRD.md
│   ├── PRD.md
│   ├── TRD.md
│   ├── ARCHITECTURE.md
│   ├── DEMO_PLAN.md
│   ├── SUBMISSION_CHECKLIST.md
│   └── SOURCE_CONTEXT.md
├── architecture/
│   ├── overview.md
│   ├── agent-roster.md
│   ├── approval-gates.md
│   ├── stripe-integration.md
│   └── model-routing.md
├── skills/
│   └── README.md
├── workflows/
│   └── README.md
├── roadmap/
│   └── phases.md
├── examples/
│   ├── founder-brief.md
│   ├── agent-run-output.md
│   └── approval-ledger-example.json
└── .github/workflows/
    └── security-scan.yml
```

## 📚 Documentation

### Business docs

- [BRD — Business Requirements](docs/BRD.md)
- [PRD — Product Requirements](docs/PRD.md)
- [TRD — Technical Requirements](docs/TRD.md)
- [Source Context](docs/SOURCE_CONTEXT.md)

### Architecture

- [System Overview](architecture/overview.md)
- [Agent Roster](architecture/agent-roster.md)
- [Approval Gates](architecture/approval-gates.md)
- [Stripe Integration](architecture/stripe-integration.md)
- [Model Routing](architecture/model-routing.md)

### Operating system

- [Skills Catalog](skills/README.md)
- [Workflows](workflows/README.md)
- [Roadmap](roadmap/phases.md)

### Submission

- [Demo Plan](docs/DEMO_PLAN.md)
- [Demo Source](demo/README.md)
- [Storyboard](demo/storyboard.md)
- [Narration Script](demo/narration-script.md)
- [Shot List](demo/shot-list.md)
- [Submission Checklist](docs/SUBMISSION_CHECKLIST.md)

## 🧪 Demo slice

Input:

> Launch Squish’s first pimple patch offer with a bundle-led Shopify funnel and creator seeding plan while keeping CAC under $18 and all claims cosmetic-safe.

Output:

- offer structure,
- funnel map,
- unit economics check,
- cosmetic-safe copy,
- creator acquisition workflow,
- Stripe action plan,
- approval ledger,
- Nemotron review packet,
- founder next actions.

## 🛣️ Roadmap

| Phase | Focus | Status |
|---|---|---|
| **Phase 0** | Public repo foundation, BRD/PRD/TRD, demo packet | ✅ Complete |
| **Phase 1** | Manual Hermes workflow producing operating artifacts | In progress |
| **Phase 2** | Scripted packet generator + validation | Planned |
| **Phase 3** | Live read-only Stripe/Nemotron proof | Planned |
| **Phase 4** | Approved Stripe Projects provisioning | Planned |
| **Phase 5** | Shopify/creator CRM/retention integrations | Planned |

## 🔗 Links

- 🏆 **Hackathon:** https://x.com/NousResearch/status/2066921443548348436
- 🕒 **Deadline reminder:** https://x.com/NousResearch/status/2071681697234420127
- 🏗️ **Built with:** [Hermes Agent](https://hermes-agent.nousresearch.com/) by Nous Research
- 🔵 **Payments/provisioning:** Stripe skills for Hermes Agent
- 🟡 **Inference review:** NVIDIA Nemotron 3 Ultra
- 🧴 **Business:** Squish skincare
