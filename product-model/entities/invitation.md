---
references:
- kind: code
  role: implementation
  target: src/pages/api/member-invites/send.ts
- kind: code
  role: implementation
  target: src/features/auth/utils/handleInvite.ts
---

# Invitation

An emailed invitation to join a sponsor's team with a role.

## Information kept

- **Email** — the address invited
- **Role** — Admin or Member
- **Expires at** — seven days after it was sent
