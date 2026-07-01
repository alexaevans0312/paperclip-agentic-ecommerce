# Roadmap — Paperclip Agentic Ecommerce

## Phase 0 — Public foundation ✅

Goal: make the repo legible as a serious hackathon submission and real business operating system.

Delivered:

- README with sponsor stack positioning.
- BRD, PRD, TRD.
- Architecture docs.
- Skills catalog.
- Workflows catalog.
- Security policy.
- Example founder brief and approval ledger.

## Phase 1 — Manual Hermes demo workflow

Goal: run the Paperclip workflow through Hermes/Cleo and save concrete artifacts.

Tasks:

- Generate `output/operating-packet.md`.
- Generate `output/unit-economics.json`.
- Generate `output/compliance-review.md`.
- Generate `output/stripe-action-plan.md`.
- Generate `output/nemotron-review-packet.md`.
- Record screen demo.

## Phase 2 — Scripted packet generator

Goal: make the workflow reproducible from a founder brief file.

Tasks:

- Add CLI script that reads `examples/founder-brief.md`.
- Validate required output sections.
- Write packet files to `output/`.
- Add tests for JSON schema and required docs.

## Phase 3 — Safe sponsor integration proof

Goal: show sponsor tooling without unsafe side effects.

Tasks:

- Install/verify Stripe skills if not already installed.
- Run safe read-only Stripe commands such as version/catalog/list.
- Generate Nemotron review packet.
- Route review to Nemotron 3 Ultra if configured.
- Record actual outputs honestly.

## Phase 4 — Approval-gated live provisioning

Goal: with Alexa approval, provision a low-risk development service.

Tasks:

- Confirm `.env` and `.projects/` are ignored.
- Confirm provider and cost.
- Set spend cap.
- Add ledger entry.
- Execute approved Stripe Projects action.
- Verify and record result.

## Phase 5 — Real Squish operating deployment

Goal: graduate from hackathon demo into the actual Squish launch operating layer.

Tasks:

- Formalise Squish skills inside Hermes.
- Connect Shopify product data once Shopify build is ready.
- Add creator CRM/tracking.
- Add weekly operator review.
- Add supplier scorecard automation.
- Add launch dashboard.

## Phase 6 — Investor-ready operating proof

Goal: use Paperclip as evidence that Squish is an agentic ecommerce company, not only a skincare brand.

Tasks:

- Produce weekly investor operating updates.
- Track time saved, CAC assumptions, task throughput, and compliance catches.
- Use Paperclip outputs in the investor deck.
