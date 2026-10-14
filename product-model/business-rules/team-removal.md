---
appliesTo:
- type: entity
  id: membership
  effect: removes
permits:
- related:
  - verb: has
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
  when:
  - entity: membership
    fact: Role
    is: Admin
- actors:
  - god-mode-user
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/members/remove.ts
---

# Admins and God Mode users remove team members

Removing someone clears the sponsor as their current sponsor.
