---
appliesTo:
- type: entity
  id: listing
- type: capability
  id: unpublish-listing
references:
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/listing/[id]/unpublish/route.ts
---

# A listing is unpublished only before its winners are announced

Unpublishing clears any selected winners, rejects every application to a project and refunds next month the credit each submission cost.
