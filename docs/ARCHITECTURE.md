# Architecture — Paperclip Agentic Ecommerce

## Architecture thesis

Paperclip is an agentic operating layer for ecommerce, not a replacement storefront. Shopify, Stripe, creator platforms, suppliers, and analytics tools remain the systems of record. Paperclip coordinates the work between them.

## Context diagram

```text
                         +-------------------------+
                         | Founder / Alexa         |
                         | taste, approvals, goals |
                         +-----------+-------------+
                                     |
                                     v
+----------------+        +-------------------------+        +-------------------+
| Squish Vault   |------->| Hermes / Cleo           |------->| GitHub Repo       |
| business plan  |        | orchestration shell     |        | docs + artifacts  |
+----------------+        +-----------+-------------+        +-------------------+
                                     |
        +----------------------------+----------------------------+
        |                            |                            |
        v                            v                            v
+----------------+          +------------------+         +----------------------+
| Agent Teams    |          | Stripe Skills    |         | Nemotron 3 Ultra     |
| strategy/ops   |          | spend/provision  |         | orchestration review |
+----------------+          +------------------+         +----------------------+
        |                            |                            |
        v                            v                            v
+----------------+          +------------------+         +----------------------+
| Operating      |          | Approval Ledger  |         | Review Result        |
| Packet         |          | audit + caps     |         | risks + decisions    |
+----------------+          +------------------+         +----------------------+
```

## Agent roles

### 1. Cleo / Hermes Orchestrator

- Owns the founder brief.
- Loads relevant business context.
- Delegates tasks to specialised agents.
- Ensures outputs are coherent and on-brand.
- Stops before sensitive side effects unless approved.

### 2. Strategy Agent

- Converts the business goal into a campaign thesis.
- Defines customer segment and buying moment.
- Connects campaign to Squish's cute-but-credible positioning.

### 3. Ecommerce Economics Agent

- Checks price, AOV, COGS, fulfillment, payment processing, CAC, and LTV.
- Flags campaigns that cannot support expected acquisition costs.
- Recommends bundle or retention adjustments.

### 4. Compliance Agent

- Reviews cosmetic/skincare claims.
- Rewrites risky language.
- Adds FTC disclosure reminders for creators.

### 5. Stripe Ops Agent

- Determines which Stripe skill applies.
- Creates a provision/purchase/payment action plan.
- Adds spend caps and environment constraints.
- Writes approval ledger entries.

### 6. Nemotron Review Layer

- Reviews the full operating packet for viability.
- Stress-tests payment/provisioning risks.
- Checks if the workflow is coherent enough for a real business.

## Stripe skills integration map

| Business need | Stripe skill | Example in Paperclip |
|---|---|---|
| Provision infrastructure | `stripe-projects` | Add a database/hosting/analytics service for creator CRM or operating dashboard |
| Buy operational services | `stripe-link-cli` | Purchase a low-cost tool, sample, or service with founder approval |
| Use paid APIs | `mpp-agent` | Call a pay-per-call enrichment or validation API with budget limit |

## Payment/process governance

Paperclip's payment philosophy:

1. Plan first.
2. Estimate cost.
3. Set cap.
4. Choose environment.
5. Ask approval.
6. Execute only if approved.
7. Verify.
8. Record result.

```text
Proposed action
  -> classify sensitivity
  -> estimate cost / provider / environment
  -> approval ledger entry
  -> founder approval
  -> Stripe skill execution
  -> verification command
  -> ledger update
```

## Nemotron orchestration pattern

Nemotron 3 Ultra is used as a review and orchestration intelligence layer, not as a payment credential holder.

Inputs:

- normalised brief,
- campaign packet,
- unit economics,
- Stripe action plan,
- compliance review,
- approval policy.

Outputs:

- viability score,
- missing dependencies,
- payment/process risks,
- recommended next action,
- presentation critique for demo.

## Data boundaries

### Safe to include in model context

- Business plan summary.
- Product assumptions.
- Unit economics estimates.
- Public documentation.
- Proposed action metadata.
- Non-sensitive supplier categories.

### Not safe to include in model context

- API keys.
- Stripe secrets.
- Payment credentials.
- Private customer data.
- Private supplier terms not meant for publication.
- `.env` or `.projects/vault` contents.

## Artifact flow

```text
examples/founder-brief.md
  -> output/brief.normalized.md
  -> output/strategy.md
  -> output/unit-economics.md
  -> output/compliance-review.md
  -> output/stripe-action-plan.md
  -> output/approval-ledger.json
  -> output/nemotron-review-packet.md
  -> output/founder-next-actions.md
```

## Why this architecture is viable

- It does not require replacing Shopify or Stripe.
- It respects founder approval for sensitive work.
- It uses Hermes where Hermes is strongest: context, skills, tools, files, memory, and workflows.
- It uses Stripe where Stripe is strongest: payments, provisioning, credentials, spend controls.
- It uses Nemotron where high-context reasoning matters: orchestration, review, and risk evaluation.
