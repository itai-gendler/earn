---
appliesTo:
- type: entity
  id: submission
  facts:
  - Payments
- type: capability
  id: pay-winner
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/add-payment.ts
---

# A bounty winner is paid in one payment; a project winner in numbered tranches

Project tranches are recorded in order, and the winner counts as paid once the payments reach the reward.
