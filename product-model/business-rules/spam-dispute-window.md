---
appliesTo:
- type: entity
  id: credit-entry
- type: capability
  id: dispute-spam-penalty
references:
- kind: code
  role: implementation
  target: src/app/api/spam-dispute/route.ts
- kind: code
  role: implementation
  target: src/features/credits/utils/canDispute.ts
---

# A spam penalty is disputed once, within seven days

The Earn team decides each dispute.
