# Product Requirements Document — Paperclip Agentic Ecommerce

## 1. Product summary

Paperclip Agentic Ecommerce is a Hermes-powered operator for DTC ecommerce brands, beginning with Squish. It converts a founder's goal into a launch-ready operating packet: business analysis, ecommerce funnel, offer strategy, compliance-safe messaging, Stripe-governed spend/provisioning actions, and execution tasks.

## 2. Product vision

A founder should be able to say:

> “Build the next Squish acquisition campaign and tell me what needs to be bought, provisioned, reviewed, and approved.”

Paperclip should return a clear, actionable operating packet and, where permitted, execute safe steps through Hermes tools and Stripe skills.

## 3. Target users

### Primary user

Founder/operator of a lean ecommerce brand.

Needs:

- fast campaign and operations planning,
- fewer scattered docs,
- compliance-safe output,
- approval control over spend/outreach,
- visibility into unit economics.

### Secondary users

- Growth operator.
- Ecommerce manager.
- Compliance/claims reviewer.
- Investor or advisor reviewing operating leverage.

## 4. Product principles

1. Real operations over theatrics.
2. Founder approval before sensitive side effects.
3. Unit economics before campaign enthusiasm.
4. Cosmetic compliance by default.
5. Stripe credentials never enter model context.
6. Agent outputs become reusable business artifacts.
7. The system should make Squish more investable, not merely more automated.

## 5. Core user stories

### US-001: Founder brief to operating packet

As a founder, I want to give Paperclip a growth goal so that it produces a structured ecommerce operating packet.

Acceptance criteria:

- Captures objective, audience, constraints, budget, and deadline.
- Produces offer, funnel, task list, metric plan, and risks.
- Uses Squish business plan assumptions.

### US-002: Offer economics check

As a founder, I want Paperclip to evaluate the economics of an offer so that I do not launch campaigns that cannot support CAC.

Acceptance criteria:

- Uses price, COGS, fulfillment, processing fees, AOV, CAC, and repeat-purchase assumptions.
- Flags weak margin or CAC risk.
- Suggests bundle/retention adjustments.

### US-003: Compliance-safe copy review

As a skincare founder, I want Paperclip to review campaign copy so that we avoid medical claims and FTC risk.

Acceptance criteria:

- Flags prohibited medical claims.
- Rewrites into cosmetic-safe language.
- Preserves brand voice.
- Notes required creator disclosure reminders.

### US-004: Stripe action planning

As a founder, I want Paperclip to identify payment/provisioning actions so that I know what needs to be bought or created.

Acceptance criteria:

- Lists proposed Stripe skill actions.
- Classifies each action as purchase, provisioning, API spend, or payment setup.
- Requires human approval before execution.
- Captures action in an approval ledger.

### US-005: Stripe Projects provisioning workflow

As an operator, I want Paperclip to prepare a Stripe Projects workflow so that ecommerce infrastructure can be provisioned safely.

Acceptance criteria:

- Checks `.gitignore` for `.env` before any credential sync.
- Initializes Stripe Projects only in the project directory.
- Runs catalog/list commands before add/upgrade/remove.
- Surfaces pricing prompts before confirmation.
- Records provider, purpose, spend cap, environment, and owner.

### US-006: Nemotron 3 Ultra operations review

As a founder, I want a high-capacity model to review the plan so that risky payment/process decisions are stress-tested before execution.

Acceptance criteria:

- Reviews workflow for viability, risk, and missing dependencies.
- Reviews spend/provisioning plan before approval.
- Produces structured recommendations.
- Does not receive raw payment credentials.

### US-007: Agent company handoff

As a founder, I want each specialised agent to leave a clear artifact so that I can resume work later.

Acceptance criteria:

- Strategy, compliance, offer, Stripe ops, and reporting outputs are separated.
- Artifacts are saved as Markdown/JSON files.
- Next actions are prioritised.

## 6. MVP features

### Feature 1: Founder Brief Intake

Inputs:

- business goal,
- product/SKU,
- target audience,
- channel,
- budget constraints,
- deadline,
- approval policy.

Outputs:

- normalised brief,
- missing-information assumptions,
- agent task plan.

### Feature 2: Ecommerce Operating Packet Generator

Outputs:

- offer structure,
- funnel map,
- creator/acquisition plan,
- messaging angles,
- compliance review,
- unit economics summary,
- founder task list.

### Feature 3: Stripe Skills Plan

Outputs:

- proposed `stripe-projects`, `stripe-link-cli`, or `mpp-agent` actions,
- approval status,
- spend caps,
- environment target,
- verification command.

### Feature 4: Approval Ledger

A structured JSON record of proposed and approved sensitive actions.

Fields:

- action id,
- type,
- requester agent,
- business reason,
- estimated cost,
- spend cap,
- tool/skill,
- approval status,
- timestamp,
- verification result.

### Feature 5: Nemotron Review Packet

A structured prompt/output packet for Nemotron 3 Ultra to review:

- business viability,
- operational risks,
- payment/provisioning risk,
- unit economics,
- compliance gaps,
- presentation clarity.

## 7. Future features

- Live Shopify product-data hygiene agent.
- Creator CRM and affiliate attribution module.
- Klaviyo/email/SMS retention workflow generator.
- Supplier scorecard automation.
- Customer review mining and SKU roadmap agent.
- Weekly investor operating dashboard.
- Stripe payment links / checkout preparation after legal and platform setup.
- Spend anomaly detection.

## 8. Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-001 | Accept founder brief as Markdown or CLI input | P0 |
| FR-002 | Load Squish business assumptions from source docs | P0 |
| FR-003 | Generate operating packet | P0 |
| FR-004 | Generate compliance review | P0 |
| FR-005 | Generate unit economics check | P0 |
| FR-006 | Generate Stripe action plan | P0 |
| FR-007 | Maintain approval ledger JSON | P0 |
| FR-008 | Produce demo-ready artifacts | P0 |
| FR-009 | Route review to Nemotron 3 Ultra when configured | P1 |
| FR-010 | Execute Stripe Projects commands when approved/configured | P1 |
| FR-011 | Connect to Shopify/Klaviyo/TikTok Shop | P2 |

## 9. Non-functional requirements

- Safety: no credential exposure in repo or transcripts.
- Auditability: every sensitive action has a ledger entry.
- Portability: docs and examples should work without paid integrations.
- Honesty: distinguish implemented, planned, and mocked demo elements.
- Latency: MVP packet generation should complete in minutes, not hours.
- Maintainability: Markdown/JSON artifacts first; app UI later.

## 10. Demo acceptance criteria

The hackathon demo is acceptable if it shows:

1. A real Squish founder brief.
2. Paperclip decomposing the brief into specialised agent workstreams.
3. A complete ecommerce operating packet.
4. Stripe skills mapped to concrete actions.
5. Nemotron 3 Ultra described or shown as orchestration/review layer.
6. Human approval gates for payment/provisioning.
7. A reusable GitHub repository with BRD, PRD, TRD, architecture, examples, and demo plan.

## 11. Open product questions

- Which Stripe skill can be demonstrated live without creating unnecessary charges?
- Is Nemotron 3 Ultra available in the current Hermes provider configuration today?
- Should the demo show a mocked Stripe approval ledger or a real dry-run/catalog/list command?
- Should the project repo be public before the demo or only after final polish?
