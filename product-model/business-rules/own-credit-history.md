---
appliesTo:
- type: entity
  id: credit-entry
  effect: reads
permits:
- related:
  - verb: earns
    entity: talent
references:
- kind: code
  role: implementation
  target: src/app/api/user/credit/history/route.ts
---

# Talent see only their own credits

The credit balance and history belong to the talent who earned them.
