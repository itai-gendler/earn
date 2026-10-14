---
appliesTo:
- type: entity
  id: submission
  effect: changes
  facts:
  - Payments
permits:
- related:
  - verb: receives
    entity: listing
  - verb: posts
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
- actors:
  - god-mode-user
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/add-payment.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/listings/verify-external-payment.ts
---

# Members of the listing's sponsor and God Mode users record payments to its winners

Payments are recorded from the Payments tab of the listing.
