---
appliesTo:
- type: entity
  id: listing
- type: capability
  id: announce-winners
references:
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/listing/[id]/announce/route.ts
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/components/PublishResults.tsx
---

# Winners are announced only once every podium place is filled

Unfilled bonus spots do not block the announcement when no other submissions remain; they are dropped from the listing's rewards. Announcing before the deadline closes the listing at once.
