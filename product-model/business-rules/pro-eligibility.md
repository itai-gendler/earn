---
appliesTo:
- type: entity
  id: talent
  effect: changes
  facts:
  - Pro
permits:
- self: true
  when:
  - fact: Total earned
    at-least: 1000
- self: true
  when:
  - fact: Superteam membership
    is: 'Yes'
references:
- kind: code
  role: implementation
  target: src/app/api/user/pro/upgrade/route.ts
---

# Talent become Pro after earning $1,000 or as Superteam members

Pro costs nothing; it is earned.
