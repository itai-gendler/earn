---
appliesTo:
- type: entity
  id: comment
- type: capability-scenario
  id: extend-deadline
references:
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/postListingSaveOperation.ts
---

# A changed deadline is announced on the listing

When a live listing's deadline changes, a deadline Comment is posted on the listing and a deadline email goes out about it.
