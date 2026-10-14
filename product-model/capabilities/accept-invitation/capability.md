---
availability:
- place: earn-web::signed-in
domain: team-settings
references:
- kind: code
  role: implementation
  target: src/features/auth/utils/handleInvite.ts
- kind: code
  role: implementation
  target: src/pages/api/member-invites/accept.ts
- kind: code
  role: implementation
  target: src/pages/earn/signup.tsx
---

# Accept an invitation

Join a sponsor's team from an emailed invitation, signed in with the invited email.
