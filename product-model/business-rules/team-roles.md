---
appliesTo:
- type: entity
  id: membership
  effect: changes
  facts:
  - Role
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
  target: src/pages/api/sponsor-dashboard/members/update-role.ts
---

# Admins and God Mode users change team roles, never their own

An Admin cannot change their own role.
