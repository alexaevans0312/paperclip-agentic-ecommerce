# Hermes Agent Skills — Paperclip Agentic Ecommerce

Paperclip is designed around specialised Hermes skills: structured, repeatable capability modules with defined reads, writes, outputs, and approval boundaries.

The skill catalog below is the intended operating surface for Squish. Some exist today as Cleo workflows; others are planned as formal Hermes skills as the project matures.

## Skill catalog

### Core ecommerce operations

| Skill | Purpose |
|---|---|
| **squish-brief-intake** | Normalise founder goals into ecommerce workstreams, constraints, assumptions, and output requirements |
| **squish-offer-economics** | Evaluate pricing, bundles, AOV, COGS, payment processing, CAC, LTV, and break-even risk |
| **squish-funnel-builder** | Build Shopify/TikTok Shop/Amazon funnel maps with metrics and drop-off risks |
| **squish-product-data** | Maintain SKU assumptions, product page fields, claim-safe feature language, and variant data |
| **squish-retention-loop** | Draft post-purchase education, review requests, and replenishment reminders |

### Compliance + brand

| Skill | Purpose |
|---|---|
| **squish-claim-bank** | Maintain allowed/rejected cosmetic claims and rewrite risky copy |
| **squish-ftc-creator-review** | Add disclosure requirements and risk notes to creator briefs |
| **squish-brand-voice** | Keep copy cute-but-credible, warm, direct, and non-clinical |

### Growth + creators

| Skill | Purpose |
|---|---|
| **squish-creator-seeding** | Generate creator targeting criteria, seeding workflow, outreach drafts, and approval gates |
| **squish-affiliate-ops** | Define affiliate offer structure, codes, links, and attribution assumptions |
| **squish-social-listening** | Monitor competitor/category signals and turn them into campaign ideas |

### Supplier + operations

| Skill | Purpose |
|---|---|
| **squish-supplier-scorecard** | Compare samples, COA/SDS/INCI docs, MOQ, lead times, pricing, and QA risk |
| **squish-launch-readiness** | Track site, product, legal, fulfillment, creative, and launch dependencies |
| **squish-weekly-operator-review** | Produce weekly review of progress, blockers, risks, and next actions |

### Stripe + spend

| Skill | Purpose |
|---|---|
| **squish-stripe-action-plan** | Map business needs to Stripe Projects, Link CLI, or MPP Agent actions |
| **squish-approval-ledger** | Create and update financial/provisioning approval records |
| **squish-spend-review** | Review proposed spend against budget, CAC, payback period, and launch priority |

### Model review

| Skill | Purpose |
|---|---|
| **squish-nemotron-review** | Build review packets for Nemotron 3 Ultra and ingest structured critique |
| **squish-presentation-qa** | Stress-test the hackathon demo against usefulness, viability, and presentation |

## Skill design pattern

Every Paperclip/Squish skill should follow this structure:

```yaml
---
name: squish-<capability>
description: "<one-line purpose>"
version: "0.1.0"
tags: [squish, ecommerce, paperclip]
---

# Skill Body
## When to Use
## Inputs
## Reads
## Writes
## Steps
## Approval Gates
## Output Format
## Safety Boundaries
```

## Design principles

- **Business-scoped** — skills read only the context relevant to their role.
- **Approval-aware** — risky actions are queued, not executed silently.
- **Unit-economics aware** — growth work must respect CAC/AOV/LTV reality.
- **Compliance-aware** — skincare claims are reviewed before use.
- **Artifact-first** — each run leaves a reusable Markdown or JSON output.
- **Honest status** — distinguish live, planned, and demo-only functionality.
