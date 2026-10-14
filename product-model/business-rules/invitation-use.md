---
appliesTo:
- type: entity
  id: invitation
  effect: removes
permits:
- actors:
  - team-member
references:
- kind: code
  role: implementation
  target: src/features/auth/utils/handleInvite.ts
---

# An invitation is used up only by the person accepting it

Invitations are never withdrawn; an unused invitation simply expires.
