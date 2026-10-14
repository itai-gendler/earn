---
appliesTo:
- type: entity
  id: listing
  facts:
  - Status
- type: capability
  id: browse-sponsor-listings
references:
- kind: code
  role: implementation
  target: src/features/listings/utils/status.ts
---

# A listing's status follows its state, deadline and payments

A published listing is In Progress until its deadline and In Review after it; once winners are announced it is Payment Pending until every winner is paid, then Completed. A draft that was live before shows as Unpublished.
