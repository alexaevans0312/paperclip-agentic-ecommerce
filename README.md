# Paperclip Agentic Ecommerce

Paperclip is an agentic ecommerce operating layer for Squish, a pre-launch skincare brand launching with premium visible hydrocolloid pimple patches.

This repository is the project foundation for the NVIDIA x Stripe x Nous Research Hermes Agent Accelerated Business Hackathon. The project is deliberately grounded in Squish's real investor plan and current operating needs: supplier validation, launch funnel design, compliant skincare messaging, creator-led acquisition, Shopify/Stripe commerce operations, and founder-approved automation.

## One-line thesis

Paperclip turns a founder's ecommerce goal into a governed operating workflow: research the opportunity, structure the offer, provision or prepare the commerce stack, generate compliant campaign assets, track unit economics, and route sensitive spend/payment actions through approval gates.

## Why this is not a fad demo

Squish already needs the operating system this project describes:

- a Shopify-led DTC launch path,
- pimple patch supplier and sample operations,
- FDA/FTC-conscious skincare claim controls,
- creator/affiliate acquisition loops,
- bundle-led AOV and repeat-purchase economics,
- investor-ready reporting,
- one founder/operator supported by durable agent memory and specialised workflows.

The hackathon version focuses this real business plan into a demonstrable agentic ecommerce system.

## Hackathon fit

The Hermes Agent Accelerated Business Hackathon asks for agents that can earn, spend, and run real operations at scale. Paperclip maps directly to that brief:

- Earn: creates and tracks acquisition opportunities, offers, bundles, creator campaigns, and funnel metrics.
- Spend: uses approval-gated Stripe skills and budget policies before buying services or provisioning infrastructure.
- Run operations: maintains a business corpus, operating dashboards, compliance guardrails, and task handoffs across specialised agents.

## Sponsor technology positioning

### Hermes Agent

Hermes is the orchestration shell: skills, memory, filesystem, browser/terminal tools, scheduled jobs, and specialised subagents.

### Stripe skills

Paperclip is designed to incorporate the Hermes Stripe payments skills:

- `stripe-link-cli`: approval-gated open-web purchasing for operational needs.
- `mpp-agent`: pay-per-call API usage for specialised services.
- `stripe-projects`: provisioning SaaS services, syncing credentials to project `.env`, and managing provider spend.

Stripe actions are never fully silent. Paperclip treats payments, subscriptions, service provisioning, and credential changes as approval-gated business events with audit trails.

### NVIDIA / Nemotron 3 Ultra

Nemotron 3 Ultra is positioned as the high-capacity reasoning layer for operations orchestration: evaluating ecommerce workflows, reconciling unit economics, stress-testing payment/provisioning steps, and supervising agent plans before execution.

In the product architecture, Nemotron 3 Ultra does not need to hold payment credentials. It reviews and orchestrates payment/process plans, while Hermes and Stripe skills execute through scoped tools and human approval gates.

## Repository map

```text
.
├── README.md
├── docs/
│   ├── BRD.md
│   ├── PRD.md
│   ├── TRD.md
│   ├── ARCHITECTURE.md
│   ├── DEMO_PLAN.md
│   ├── SUBMISSION_CHECKLIST.md
│   └── SOURCE_CONTEXT.md
├── examples/
│   ├── founder-brief.md
│   ├── agent-run-output.md
│   └── approval-ledger-example.json
└── .gitignore
```

## Demo narrative

1. Founder gives Paperclip a real Squish growth goal.
2. Paperclip decomposes it into ecommerce operating workstreams.
3. Specialist agents produce acquisition, offer, compliance, and infrastructure plans.
4. Nemotron 3 Ultra acts as orchestration/review layer for business viability and payment safety.
5. Stripe skills are represented as approval-gated actions: provision, pay, or prepare checkout infrastructure.
6. Paperclip outputs a launch-ready operating packet: offer, funnel, tasks, spend plan, and audit trail.

## Current status

Documentation foundation complete. Implementation target is a demoable Hermes workflow that can run locally, produce real artifacts, and show Stripe/NVIDIA integration points without pretending to have completed live paid actions.

## References

- Hackathon announcement: https://x.com/NousResearch/status/2066921443548348436
- Deadline reminder: https://x.com/NousResearch/status/2071681697234420127
- Stripe skills announcement: https://x.com/NousResearch/status/2066647737613832624
- Stripe Projects in Hermes docs: https://hermes-agent.nousresearch.com/docs/user-guide/skills/optional/payments/payments-stripe-projects
- Stripe Projects blog: https://stripe.com/blog/stripe-projects-adds-new-agents-providers-developer-controls
