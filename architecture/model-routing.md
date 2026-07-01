# Model Routing — Nemotron 3 Ultra + Hermes

Paperclip uses model routing based on task type and data sensitivity.

## Routing principle

The best model is not always the biggest model. Paperclip routes work by:

1. sensitivity,
2. task complexity,
3. context length,
4. cost,
5. required tool use.

## Proposed model roles

| Role | Model | Use |
|---|---|---|
| Founder orchestrator | GPT-5.5 / active Hermes model | Cleo synthesis, repo work, code/docs, tool use |
| Operations reviewer | NVIDIA Nemotron 3 Ultra | Long-context business plan review, viability critique, payment/provisioning risk review |
| Fast classification | Smaller low-cost model | Bulk tagging, routine checks |
| Creative generation | Current creative model stack | Campaign concepts, visual prompts, demo assets |
| Local/private fallback | Local model if configured | Sensitive data or offline operations |

## Nemotron review packet

Nemotron should receive:

- business goal,
- source context summary,
- offer economics,
- compliance review,
- Stripe action plan,
- approval policy,
- open risks.

Nemotron should not receive:

- API keys,
- Stripe secrets,
- payment credentials,
- private supplier negotiations,
- customer PII.

## Review output schema

```json
{
  "viability_score": "1-10",
  "unit_economics_risk": "low|medium|high",
  "payment_risk": "low|medium|high",
  "compliance_risk": "low|medium|high",
  "missing_dependencies": [],
  "recommended_next_actions": [],
  "demo_presentation_notes": []
}
```

## Why Nemotron belongs here

Agentic ecommerce needs judgment under context: CAC assumptions, supplier risk, payment/provisioning boundaries, claim compliance, and investor legibility. Nemotron 3 Ultra is positioned as the reviewer that stress-tests those decisions before Hermes executes scoped actions.
