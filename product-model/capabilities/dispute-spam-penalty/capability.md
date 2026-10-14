---
availability:
- place: earn-web::signed-in
domain: credits
references:
- kind: code
  role: implementation
  target: src/app/api/spam-dispute/route.ts
- kind: code
  role: implementation
  target: src/features/credits/components/DisputeModal.tsx
- kind: code
  role: implementation
  target: src/features/credits/utils/canDispute.ts
---

# Dispute a spam penalty

Ask the Earn team to review a spam penalty within seven days of it.
