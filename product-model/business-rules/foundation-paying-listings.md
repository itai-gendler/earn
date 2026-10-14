---
appliesTo:
- type: entity
  id: listing
  facts:
  - Foundation paying
- type: capability
  id: submit-kyc
- type: capability
  id: announce-winners
references:
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/isFndnPayingCheck.ts
- kind: code
  role: implementation
  target: src/features/listings/utils/createPayment.ts
---

# Superteam pays the winners of foundation-paid listings once they pass KYC

Only a Superteam chapter's bounties and hackathon tracks may be foundation paid. Their winners verify their identity before Superteam pays them, and the sponsor pays nothing from the dashboard.
