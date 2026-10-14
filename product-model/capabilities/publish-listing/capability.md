---
availability:
- place: earn-web::signed-in
domain: my-listings
references:
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/listing/[id]/publish/route.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/sponsorVerification.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/listingTransformationPipe.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/components/Form/PrePublish/Modal.tsx
---

# Publish a listing

Publish a draft after choosing its visibility, region, Pro only, agent access, address and, for Superteam chapters, foundation paying.
