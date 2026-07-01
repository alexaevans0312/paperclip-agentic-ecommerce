# Security Policy

Paperclip Agentic Ecommerce is built around founder-approved operations, safe public documentation, and careful handling of ecommerce/payment credentials.

## Public repository boundary

This public repo may include:

- sanitized Squish business context,
- architecture docs,
- example workflows,
- sample approval ledgers,
- demo scripts,
- non-sensitive operating assumptions.

This public repo must not include:

- `.env` files,
- Stripe secrets or webhook secrets,
- API keys or OAuth tokens,
- private supplier quotes or negotiations,
- customer data,
- payment credentials,
- unpublished account details,
- private vault exports.

## Sensitive action policy

Paperclip separates planning from execution.

| Tier | Policy |
|---|---|
| Tier 0 | Local drafting/analysis may run without interruption |
| Tier 1 | Low-risk public lookups may run with visible logging |
| Tier 2 | Outreach, public posting, purchases, provisioning, and paid API calls require explicit approval |
| Tier 3 | Live customer charges, production payment changes, credential rotation, and paid plan upgrades are forbidden until configured and approved |

## Stripe safety

- Stripe credentials stay in Stripe/Hermes/tool storage, not prompts or repo files.
- `stripe-projects` must only run inside a project with `.env` and `.projects/` ignored.
- Paid provider actions must surface cost, cap, environment, and business reason before approval.
- Every proposed financial action should be represented in an approval ledger.

## Model safety

Nemotron 3 Ultra and other cloud models receive review packets, not payment credentials or private customer data. Sensitive ecommerce data should be classified before routing.

## Reporting issues

If this repository accidentally exposes sensitive data, remove public access immediately, rotate affected credentials, and replace the commit history if necessary before continuing demo work.
