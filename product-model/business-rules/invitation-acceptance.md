---
appliesTo:
- type: entity
  id: invitation
- type: capability
  id: accept-invitation
references:
- kind: code
  role: implementation
  target: src/features/auth/utils/handleInvite.ts
---

# An invitation is accepted only by the invited email, within seven days

Accepting joins the team with the role in the invitation and uses the invitation up.
