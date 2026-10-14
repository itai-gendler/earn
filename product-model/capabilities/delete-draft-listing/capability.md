---
availability:
- place: earn-web::signed-in
domain: my-listings
references:
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/listing/[id]/delete/route.ts
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/components/Modals/DeleteDraftModal.tsx
---

# Delete a draft listing

Delete a listing that was never published.
