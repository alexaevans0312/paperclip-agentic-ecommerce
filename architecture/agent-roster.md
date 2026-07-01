# Agent Roster

Paperclip uses a company-like agent structure so each operating function has a clear responsibility, authority scope, and approval boundary.

## Core roster

| Agent | Role | Primary outputs | Authority |
|---|---|---|---|
| **Cleo** | Founder-side orchestrator / brand operator | Final operating packet, synthesis, decisions for Alexa | Can delegate, draft, verify; cannot spend/post/outreach without approval |
| **Mira** | Ecommerce strategist | Offer thesis, funnel, target segment, creative angle | Draft and recommend |
| **Ledger** | Unit economics analyst | AOV/CAC/COGS/LTV check, margin warnings | Analyze and flag risk |
| **Vera** | Claims + FTC compliance | Approved/rejected claim bank, disclosure notes | Block risky copy until revised |
| **Atlas** | Supplier + operations tracker | Sample plan, vendor dependencies, QA/documentation checklist | Track and recommend |
| **Piper** | Creator acquisition operator | Creator brief, seeding workflow, affiliate plan | Draft only; outreach requires approval |
| **Nova** | Stripe ops agent | Stripe action plan, approval ledger, spend caps | Queue financial/provisioning actions only |
| **Nemo** | Nemotron review layer | Viability/risk/presentation critique | Review and recommend; no credentials |

## Delegation pattern

```json
{
  "from": "cleo",
  "to": "nova",
  "task_type": "stripe_action_plan",
  "context": {
    "goal": "launch bundle-led creator acquisition campaign",
    "budget_policy": "no spend without approval",
    "environment": "development"
  },
  "authority_scope": "plan_only",
  "requires_approval_before_action": true
}
```

## Response pattern

```json
{
  "from": "nova",
  "to": "cleo",
  "status": "completed",
  "result": {
    "recommended_skill": "stripe-projects",
    "reason": "provision campaign tracking database",
    "estimated_cost": "TBD from catalog",
    "spend_cap": "$25/month development"
  },
  "approval_needed": "founder_explicit"
}
```

## Budget policy

| Agent | Token/API budget | Spend authority |
|---|---|---|
| Cleo | High | Can queue, not execute |
| Mira | Medium | None |
| Ledger | Medium | None |
| Vera | Medium | None |
| Atlas | Medium | None |
| Piper | Medium | None |
| Nova | Medium | Can prepare Stripe actions; execution requires approval |
| Nemo | High-context review only | None |

If an agent needs more budget, more authority, or external access, it escalates to Cleo, then to Alexa.
