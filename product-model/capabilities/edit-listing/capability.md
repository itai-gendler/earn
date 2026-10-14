---
availability:
- place: earn-web::signed-in
domain: my-listings
references:
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/listing/[id]/update/route.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/isListingEditAllowed.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/postListingSaveOperation.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/types/schema.ts
---

# Edit a listing

Change a listing's details and rewards: a draft as you write, a live listing until its deadline.
