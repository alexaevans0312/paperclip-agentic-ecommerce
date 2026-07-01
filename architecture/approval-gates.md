# Approval Gates

Paperclip separates thinking from acting. This is essential for ecommerce because money, public posts, creator outreach, supplier commitments, and customer data all carry risk.

## Gate tiers

| Tier | Name | What is allowed | Examples |
|---|---|---|---|
| 0 | Silent allowed | Local drafting, analysis, artifact generation | Generate BRD, calculate AOV, draft claim-safe copy |
| 1 | Visible confirmation | Low-risk public reads or reversible local actions | Read public docs, inspect repo, run local validation |
| 2 | Explicit approval | External side effects or financial/provisioning intent | Post on X, send outreach, provision SaaS, buy a tool |
| 3 | Launch-forbidden until configured | Production financial/customer actions | Charge customers, rotate credentials, upgrade paid plans |

## Financial action lifecycle

```text
Proposed financial action
  -> classify action type
  -> estimate cost
  -> assign spend cap
  -> choose environment
  -> create ledger entry
  -> request founder approval
  -> execute via Stripe skill if approved
  -> verify
  -> update ledger
```

## Approval ledger fields

- action id,
- action type,
- requesting agent,
- business reason,
- estimated cost,
- spend cap,
- provider/tool,
- environment,
- approver,
- verification command,
- final status.

## Practical rule

If Paperclip would make the founder nervous after the fact, it must ask first.
