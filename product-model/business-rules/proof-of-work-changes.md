---
appliesTo:
- type: entity
  id: proof-of-work
  effect: changes
permits:
- related:
  - verb: adds
    entity: talent
references:
- kind: code
  role: implementation
  target: src/pages/api/pow/edit.ts
---

# Talent edit only their own Proof of Work

Proof of Work belongs to the talent whose profile shows it.
