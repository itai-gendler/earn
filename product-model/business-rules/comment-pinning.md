---
appliesTo:
- type: entity
  id: comment
  effect: changes
  facts:
  - Pinned
permits:
- related:
  - verb: has
    entity: listing
  - verb: is point of contact for
    entity: team-member
references:
- kind: code
  role: implementation
  target: src/pages/api/comment/[id]/pin.ts
- kind: code
  role: implementation
  target: src/pages/api/comment/create.ts
---

# Only the listing's point of contact pins its comments

Only a top-level comment can be pinned.
