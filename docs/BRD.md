# Business Requirements Document — Paperclip Agentic Ecommerce

## 1. Purpose

Paperclip Agentic Ecommerce is a Hermes-powered operating layer for Squish, a pre-launch skincare ecommerce company. It converts founder goals into governed ecommerce operations: market insight, offer structure, compliant customer messaging, creator acquisition, Stripe-ready commerce actions, and operating reports.

This BRD defines the business need, stakeholders, success criteria, and non-negotiable constraints for the hackathon project and the longer-term Squish operating system.

## 2. Business context

Squish is launching with premium visible hydrocolloid pimple patches. The business plan depends on:

- DTC launch via Shopify.
- Creator/social discovery.
- Bundle-led first purchase.
- Repeat purchase and SKU expansion.
- Careful FDA/FTC cosmetic claim discipline.
- Low fixed cost before product-market fit.
- An agentic operating model that lets one founder manage more surface area than a traditional early team.

The hackathon asks for agents that can earn, spend, and run real operations. Squish is an ideal proving ground because ecommerce requires all three:

- Earn: acquire customers, structure offers, improve conversion, retain buyers.
- Spend: sample orders, SaaS provisioning, creator seeding, API usage, infrastructure.
- Run operations: supplier tracking, compliance, product data, reporting, workflows.

## 3. Business problem

Early ecommerce brands often fail because the founder is forced to manually coordinate too many fragile workflows:

- supplier research and sample comparison,
- product positioning,
- claims and compliance checks,
- content and creator campaigns,
- ecommerce setup,
- checkout and payment operations,
- unit economics and cash planning,
- post-purchase retention.

The result is slow execution, inconsistent memory, avoidable compliance risk, and poor visibility into whether growth activities can actually make money.

## 4. Business opportunity

Paperclip gives Squish a lean operating advantage:

- Founder taste remains central.
- Agents handle repeatable analysis, drafting, monitoring, and structured handoffs.
- Stripe skills allow infrastructure/payment actions to become governed workflows rather than manual dashboard clicking.
- Nemotron 3 Ultra can provide high-capacity reasoning for operational orchestration, viability review, and safety checks.
- Hermes memory and skills preserve decisions across sessions.

## 5. Objectives

### Hackathon objectives

1. Demonstrate a real agentic ecommerce workflow grounded in Squish.
2. Show how Hermes orchestrates specialised business agents.
3. Incorporate Stripe skills as a credible mechanism for spend, SaaS provisioning, and payment-related workflows.
4. Position Nemotron 3 Ultra as the reasoning/orchestration layer for payment/process review.
5. Produce reusable project documentation: BRD, PRD, TRD, architecture, and demo plan.
6. Avoid claiming live autonomous spending unless actually executed and approved.

### Business objectives

1. Reduce founder operating load before launch.
2. Improve launch speed without weakening brand taste or compliance quality.
3. Create a repeatable ecommerce operating packet for each growth goal.
4. Track unit economics at every acquisition decision.
5. Build a durable operating corpus investors can understand.

## 6. Stakeholders

| Stakeholder | Need |
|---|---|
| Founder/operator | Faster execution, fewer scattered decisions, approval control |
| Customers | Clear, honest product education and smooth purchase experience |
| Creators/affiliates | Clear offers, tracking, compliant disclosure expectations |
| Investors | Evidence that agentic operations reduce cost and increase velocity |
| Compliance reviewer | Claim-safe messaging and documented review trails |
| Stripe/payment operator | Safe spend, scoped credentials, traceable provisioning |
| Technical maintainer | Clear architecture, minimal secrets risk, reproducible workflows |

## 7. Scope

### In scope for hackathon demo

- Founder brief ingestion.
- Agentic decomposition into ecommerce workstreams.
- Offer/funnel generation using Squish unit economics.
- Compliance claim review for skincare copy.
- Stripe action plan: payment/provisioning/spend steps with approval gates.
- Nemotron 3 Ultra orchestration/review role in the workflow.
- Structured output artifacts.
- Audit trail for proposed spend/payment actions.
- Demo-ready README and project docs.

### Out of scope for hackathon demo

- Fully autonomous live purchasing without human approval.
- Medical/acne-treatment claims.
- Real customer outreach without Alexa approval.
- Storing payment credentials in model context.
- Production Shopify deployment unless separately approved.
- Pretending integration is live if it is only designed or mocked.

## 8. Business requirements

### BR-001: Real-business grounding

Paperclip must use Squish's actual business plan, product assumptions, and launch constraints as its operating foundation.

### BR-002: Agentic ecommerce workflow

Paperclip must show more than copy generation. It must convert a business goal into ecommerce operating artifacts: offer, funnel, infrastructure plan, tasks, metrics, and approval ledger.

### BR-003: Stripe-governed operations

Paperclip must identify where Stripe skills fit:

- `stripe-projects` for provisioning SaaS/infrastructure.
- `stripe-link-cli` for approval-gated purchases.
- `mpp-agent` for pay-per-call API usage.

### BR-004: NVIDIA/Nemotron orchestration

Paperclip must define how Nemotron 3 Ultra contributes: high-context operational reasoning, viability checks, payment-plan review, and multi-agent orchestration oversight.

### BR-005: Approval gates

Payment, provisioning, outreach, account creation, and data-sharing actions must require explicit approval and produce an audit record.

### BR-006: Compliance guardrails

Skincare copy must stay in cosmetic-safe language and avoid explicit medical claims such as “treats acne” or “cures acne.”

### BR-007: Unit economics awareness

Every acquisition or offer recommendation must consider price, AOV, COGS, fulfillment, processing, CAC, LTV, and repeat purchase assumptions.

### BR-008: Investor legibility

Outputs must make the operating leverage visible: lower fixed payroll, faster iteration, less agency dependence, better memory, clearer reporting.

## 9. Success metrics

### Demo success

- A viewer understands the business use case within 30 seconds.
- The demo shows a real operational workflow, not a generic chatbot.
- Stripe and NVIDIA are integrated into the system logic clearly and credibly.
- The repository explains what is built, what is planned, and what is deliberately approval-gated.

### Business success

- Time from growth goal to operating packet: under 10 minutes.
- Compliance review applied to every customer-facing claim.
- Spend/provisioning actions captured in approval ledger before execution.
- Each campaign packet includes unit economics assumptions.
- Founder has a clear next-action list.

## 10. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Looks like an AI marketing toy | Anchor demo in ecommerce operations, unit economics, Stripe, and approval flows |
| Overclaims autonomous spending | Show approval-gated spend design and be transparent about execution state |
| Compliance risk | Maintain cosmetic claim bank and prohibited-claim checks |
| Payment credential leakage | Never put credentials in prompts or repo; use Stripe Projects vault/.env hygiene |
| Too broad for deadline | Demo one vertical slice: growth goal -> offer -> Stripe action plan -> operating packet |
| Sponsor tech feels bolted on | Make Stripe/Nemotron central to operating control, not decorative logos |

## 11. Recommended demo slice

Input:

> Launch Squish's first pimple patch offer with a bundle-led Shopify funnel and creator seeding plan while keeping CAC under $18 and all claims cosmetic-safe.

Output:

- Offer structure.
- Funnel map.
- Creator acquisition plan.
- Compliance claim review.
- Stripe provisioning/spend plan.
- Nemotron orchestration review.
- Approval ledger.
- Founder task list.
