---
appliesTo:
- type: entity
  id: listing
- type: capability
  id: create-listing
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/listings/is-create-allowed.ts
- kind: code
  role: implementation
  target: src/layouts/Sponsor.tsx
---

# A sponsor with five overdue results cannot start a listing

While five or more of a sponsor's live listings are past their deadline without winners announced, the sponsor cannot start another listing.
