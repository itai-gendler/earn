---
appliesTo:
- type: entity
  id: listing
  facts:
  - Deadline
- type: capability
  id: edit-listing
- type: capability
  id: publish-listing
references:
- kind: code
  role: implementation
  target: src/features/listing-builder/types/schema.ts
---

# A deadline is set in the future and extended by at most two weeks

A listing's deadline cannot be set in the past, and a live listing's deadline moves at most two weeks past the one it had. God Mode users are not held to either limit.
