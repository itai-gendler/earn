---
appliesTo:
- type: entity
  id: sponsor
  effect: creates
permits:
- actors:
  - team-member
  when:
  - entity: team-member
    fact: Current sponsor
    absent: true
- actors:
  - god-mode-user
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsors/create.ts
---

# A person creates a sponsor only while they work for none; God Mode users create any number

Whoever creates a sponsor joins its team as Admin.
