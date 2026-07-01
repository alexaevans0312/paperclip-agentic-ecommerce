# Technical Requirements Document — Paperclip Agentic Ecommerce

## 1. Technical purpose

This TRD defines the system architecture and implementation requirements for Paperclip Agentic Ecommerce: a Hermes Agent workflow that turns a Squish business goal into an ecommerce operating packet and approval-gated Stripe/NVIDIA orchestration plan.

## 2. System overview

Paperclip is implemented as an agentic workflow, not initially as a monolithic application.

Core runtime:

- Hermes Agent as orchestration shell.
- Markdown/JSON files as durable artifacts.
- Stripe skills for payments/provisioning/spend workflows.
- Nemotron 3 Ultra as optional high-capacity orchestration/review model.
- Human approval gates for sensitive side effects.

## 3. High-level architecture

```text
Founder Brief
  |
  v
Hermes Orchestrator / Cleo
  |
  +--> Strategy Agent
  |      - audience, positioning, offer thesis
  |
  +--> Ecommerce Economics Agent
  |      - price, AOV, COGS, CAC, LTV, contribution risk
  |
  +--> Compliance Agent
  |      - skincare claims, FTC disclosure, prohibited wording
  |
  +--> Stripe Ops Agent
  |      - provisioning plan, purchase plan, spend caps, approval ledger
  |
  +--> Nemotron Review Layer
  |      - viability review, orchestration critique, risk check
  |
  v
Operating Packet
  - offer
  - funnel
  - claims-safe copy
  - Stripe action plan
  - approval ledger
  - founder tasks
```

## 4. Core modules

### 4.1 Brief Intake

Responsibilities:

- Parse founder goal.
- Attach Squish context.
- Identify constraints: budget, channel, product, deadline, compliance lane.
- Produce `brief.normalized.md`.

Inputs:

- `examples/founder-brief.md` or direct Hermes prompt.
- Squish source context.

Outputs:

- Normalised brief.
- Assumption list.
- Required specialist tasks.

### 4.2 Strategy Agent

Responsibilities:

- Define customer segment.
- Define campaign angle.
- Define offer thesis.
- Connect output to Squish's cute-but-credible positioning.

Outputs:

- `strategy.md`
- campaign angle table,
- key risks,
- next tests.

### 4.3 Ecommerce Economics Agent

Responsibilities:

- Estimate offer contribution.
- Check AOV/CAC viability.
- Flag margin problems.
- Recommend bundles or retention changes.

Inputs:

- $16 pack retail price.
- $15.20 net revenue per pack.
- $3.20 landed COGS estimate.
- $5.50 fulfillment/order estimate.
- 2.9% + $0.30 payment processing proxy.
- CAC target $14-18.

Outputs:

- `unit-economics.md`
- `unit-economics.json`

### 4.4 Compliance Agent

Responsibilities:

- Review claims and copy.
- Reject explicit treatment/cure claims.
- Rewrite into cosmetic-safe language.
- Add FTC creator disclosure reminders.

Rules:

- Avoid “treats acne,” “cures acne,” “heals acne,” “prevents acne,” or drug-like claims.
- Prefer “helps absorb fluid,” “protects from picking,” “supports an ideal healing environment,” “designed for surface whiteheads,” and “users report.”

Outputs:

- `compliance-review.md`
- accepted claim bank,
- rejected claim examples.

### 4.5 Stripe Ops Agent

Responsibilities:

- Determine which Stripe skill applies.
- Prepare command plan but do not execute paid actions without approval.
- Check `.gitignore` before `.env` writes.
- Define spend caps and environment.
- Create approval ledger entries.

Skills:

- `stripe-projects`: provision SaaS services and sync credentials to `.env`.
- `stripe-link-cli`: buy things on the open web with safety limits.
- `mpp-agent`: use pay-per-call APIs.

Required guardrails:

- Never commit `.env`.
- Never expose credentials to model output.
- Run `stripe projects catalog` before suggesting providers.
- Run `stripe projects list` for verification after approved changes.
- Surface tier/pricing prompts before confirmation.

Outputs:

- `stripe-action-plan.md`
- `approval-ledger.json`

### 4.6 Nemotron Review Layer

Responsibilities:

- Review the plan at high context.
- Identify missing operational dependencies.
- Stress-test payment/provisioning steps.
- Score viability and presentation clarity.

Modes:

- If Nemotron 3 Ultra is configured: route review to the model.
- If not configured: generate the review packet and mark execution as pending.

Critical rule:

Nemotron receives operational context, not payment credentials.

Outputs:

- `nemotron-review-packet.md`
- `nemotron-review-result.md` when run.

## 5. Data model

### 5.1 Approval ledger

```json
{
  "actions": [
    {
      "id": "stripe-projects-001",
      "type": "provision_saas",
      "skill": "stripe-projects",
      "requested_by": "stripe-ops-agent",
      "business_reason": "Provision database for creator CRM and campaign tracking",
      "estimated_cost": "TBD from provider catalog",
      "spend_cap": "$25/month development",
      "environment": "development",
      "status": "pending_founder_approval",
      "requires_human_approval": true,
      "verification_command": "stripe projects list",
      "created_at": "2026-06-30T00:00:00Z"
    }
  ]
}
```

### 5.2 Operating packet

```json
{
  "brief_id": "squish-launch-001",
  "goal": "Launch bundle-led pimple patch acquisition campaign",
  "offer": {},
  "funnel": {},
  "unit_economics": {},
  "compliance": {},
  "stripe_actions": [],
  "founder_tasks": []
}
```

## 6. Repository requirements

- Markdown docs must explain the system clearly without needing private vault access.
- Example files must be safe to publish.
- `.env`, `.projects/`, credential files, exports, and local logs must be ignored.
- Any copied business data must avoid secrets and private supplier details.

## 7. Security requirements

| ID | Requirement |
|---|---|
| SEC-001 | Do not commit `.env`, `.projects/`, API keys, tokens, payment credentials, or private supplier records |
| SEC-002 | Sensitive actions require approval ledger entry |
| SEC-003 | Payment/provisioning actions require explicit founder approval |
| SEC-004 | Credentials must remain in Stripe/Hermes/tool storage, not model context |
| SEC-005 | Demo examples must not imply live spending unless verified |

## 8. Integration requirements

### Hermes Agent

- Skills used: project, funnel-builder, hermes-agent, github-operations, xurl, computer-use if needed.
- Future payment skills to install when executing live Stripe portion:
  - `official/payments/stripe-projects`
  - `official/payments/stripe-link-cli`
  - `official/payments/mpp-agent`

### Stripe Projects

Prerequisites before live use:

- Stripe CLI installed.
- Stripe Projects plugin installed.
- Stripe account authenticated.
- Project `.gitignore` protects `.env` and `.projects/`.
- User approval for any provider add/upgrade/payment action.

### NVIDIA / Nemotron 3 Ultra

Prerequisites before live use:

- Provider route configured in Hermes or accessible through approved API path.
- Model invocation logged as review/orchestration, not credential execution.
- Review packet saved for audit/demo.

## 9. Implementation phases

### Phase 0: Documentation foundation

- README.
- BRD.
- PRD.
- TRD.
- Architecture.
- Demo plan.
- Example artifacts.

### Phase 1: Manual Hermes demo workflow

- Run the workflow through Cleo/Hermes manually.
- Save generated operating packet artifacts.
- Show Stripe/Nemotron action plan and approval ledger.

### Phase 2: Scripted packet generator

- Add a CLI script that reads a founder brief and source context.
- Emits Markdown/JSON packet files.
- Adds validation for required sections.

### Phase 3: Live integration proof

- Install Stripe skills.
- Run safe read-only commands such as catalog/list/version.
- Optional approved development provisioning if useful and low-cost.
- Route review packet through Nemotron 3 Ultra if configured.

## 10. Verification plan

- `git status` clean before publishing.
- Confirm `.gitignore` includes `.env` and `.projects/`.
- Confirm all required docs exist.
- Confirm examples are valid JSON/Markdown.
- Confirm README links to hackathon, Stripe skills, and docs.
- Confirm no secrets in repo with a grep-style scan.
- Confirm GitHub repo is reachable after push.

## 11. Known constraints

- Live Stripe actions may incur charges and require explicit approval.
- Nemotron 3 Ultra availability must be verified in the active Hermes/provider configuration.
- This documentation foundation is intentionally honest about planned vs implemented integrations.
- The demo should avoid claiming fully autonomous business operation before the workflow is actually exercised.
