---
appliesTo:
- type: entity
  id: sponsor
  effect: changes
permits:
- related:
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
- actors:
  - god-mode-user
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsors/edit.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsors/update-entity-name.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsor/verification.ts
---

# Members of a sponsor's team and God Mode users change the sponsor

Admins and Members alike keep the sponsor profile.
