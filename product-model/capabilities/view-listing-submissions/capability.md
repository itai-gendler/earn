---
availability:
- place: earn-web::public
- place: earn-web::signed-in
references:
- kind: code
  role: implementation
  target: src/pages/api/listings/submissions/[slug].ts
- kind: code
  role: implementation
  target: src/pages/api/listings/[listingId]/winners.ts
- kind: code
  role: implementation
  target: src/pages/earn/listing/[slug]/winner.tsx
---

# View listing results

See a listing's winners by position and every submission once its winners are announced.
