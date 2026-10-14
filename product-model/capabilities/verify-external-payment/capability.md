---
availability:
- place: earn-web::signed-in
domain: payments
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/listings/verify-external-payment.ts
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/components/Modals/VerifyPayment.tsx
---

# Verify an external payment

Record payments made outside Earn by giving their transaction links; Earn verifies each before recording it.
