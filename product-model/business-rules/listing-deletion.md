---
appliesTo:
- type: entity
  id: listing
  effect: removes
permits:
- related:
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
  target: src/app/api/sponsor-dashboard/listing/[id]/delete/route.ts
---

# Members of the listing's sponsor and God Mode users delete draft listings

Only a listing that was never published can be deleted; a live listing is unpublished instead.
