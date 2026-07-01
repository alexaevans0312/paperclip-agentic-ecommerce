# Stripe Integration — Earn, Spend, Provision

Paperclip uses Stripe as the governed commerce action layer for Squish.

## Design philosophy

The hackathon asks for agents that can earn, spend, and run operations. For ecommerce, Stripe is not decorative. It is where offers, payment links, invoices, SaaS provisioning, API usage, and operational spend become real.

Paperclip's rule:

> No money moves silently. Every financial action has a reason, limit, approval state, and verification trail.

## EARN — revenue operations

Potential Squish revenue workflows:

- Draft bundle offer structure.
- Prepare Stripe/Shopify checkout configuration requirements.
- Generate payment-link or checkout plan for preorders when approved.
- Track campaign source, AOV, and conversion intent.
- Prepare post-purchase/replenishment logic.

### Example earn flow

```text
Campaign offer approved
  -> Paperclip defines bundle SKUs and price logic
  -> Nova prepares checkout/payment setup plan
  -> Alexa approves live setup
  -> Stripe/Shopify payment path is created or updated
  -> conversion metrics feed back into Ledger
```

## SPEND — expense management

Potential Squish spend workflows:

| Spend category | Example | Approval |
|---|---|---|
| Supplier/sample | order sample packs, packaging proofs | Tier 2 explicit |
| Creator seeding | product shipment, creator fee, paid brief | Tier 2 explicit |
| SaaS | analytics, database, dashboard, email tool | Tier 2 explicit |
| API usage | enrichment, validation, monitoring | Tier 2 batch cap |
| Production/customer money movement | live customer charge/refund changes | Tier 3 until configured |

## PROVISION — Stripe Projects

`stripe-projects` can provision services and sync credentials. Paperclip treats this as infrastructure spend with credential risk.

Required steps before live provisioning:

1. Confirm `.env` and `.projects/` are ignored.
2. Run `stripe projects catalog`.
3. Choose provider and service.
4. Set environment: development/staging/production.
5. Set spend cap.
6. Create approval ledger entry.
7. Ask Alexa to approve.
8. Execute only after approval.
9. Verify with `stripe projects list`.

## Hermes Stripe skills fit

| Skill | Use in Paperclip |
|---|---|
| `stripe-projects` | Provision development services for creator CRM, campaign tracking, analytics, or demo infrastructure |
| `stripe-link-cli` | Buy tools/research/resources on the open web with spending caps |
| `mpp-agent` | Use pay-per-call APIs for enrichment or ecommerce intelligence under a budget |

## Example action record

```json
{
  "action": "stripe_projects_add_provider",
  "actor": "nova",
  "business_reason": "Need development database for creator campaign tracking",
  "provider": "TBD from catalog",
  "environment": "development",
  "spend_cap": "$25/month",
  "approval_required": true,
  "status": "pending_founder_approval"
}
```

## Demo stance

For the hackathon demo, Paperclip can credibly show Stripe in three levels:

1. **Architecture proof:** docs + approval ledger + command plan.
2. **Read-only proof:** safe commands such as catalog/list/version.
3. **Live proof:** approved low-cost development provisioning if Alexa chooses.

The repo must be honest about which level has been executed.
