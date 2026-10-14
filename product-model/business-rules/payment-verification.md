---
appliesTo:
- type: entity
  id: submission
  facts:
  - Payments
- type: capability
  id: pay-winner
- type: capability
  id: verify-external-payment
references:
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/utils/paymentRPCValidation.ts
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/utils/paymentReplayCheck.ts
---

# A payment is recorded only when its transaction matches the reward

The transaction must have succeeded on chain, paid the winner's wallet in the listing's reward token and for the amount entered, and not have been recorded before.
