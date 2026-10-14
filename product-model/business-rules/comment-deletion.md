---
appliesTo:
- type: entity
  id: comment
  effect: removes
permits:
- related:
  - verb: writes
    entity: talent
- related:
  - verb: writes
    entity: team-member
references:
- kind: code
  role: implementation
  target: src/pages/api/comment/[id]/delete.ts
---

# Only its author deletes a comment

Deleting a comment deletes its replies with it.
