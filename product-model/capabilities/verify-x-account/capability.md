---
availability:
- place: earn-web::signed-in
references:
- kind: code
  role: implementation
  target: src/pages/api/auth/[...nextauth].ts
- kind: code
  role: implementation
  target: src/features/social/utils/x-verification.ts
- kind: code
  role: implementation
  target: src/features/social/components/XVerificationModal.tsx
---

# Verify an X account

Prove ownership of an X account by signing in to X, so that X links to it are accepted in submissions.
