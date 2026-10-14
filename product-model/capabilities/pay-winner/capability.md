---
availability:
- place: earn-web::signed-in
domain: payments
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/add-payment.ts
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/components/Submissions/PayoutButton.tsx
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/utils/paymentRPCValidation.ts
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/utils/paymentReplayCheck.ts
---

# Pay a winner

Pay a winner's reward from the sponsor's own Solana wallet; Earn verifies the transaction and records the payment.
