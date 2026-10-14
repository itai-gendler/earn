---
appliesTo:
- type: entity
  id: scout
  effect: changes
  facts:
  - Invited
permits:
- related:
  - verb: recommends
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
  target: src/app/api/sponsor-dashboard/listing/[id]/scout/invite/[userId]/route.ts
---

# Members of the listing's sponsor and God Mode users invite scouts, at most ten per listing

Recommendations are offered only while a listing is live and its winners are not announced.
