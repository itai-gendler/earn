---
appliesTo:
- type: entity
  id: submission
- type: capability
  id: submit-to-bounty
- type: capability
  id: apply-to-project
references:
- kind: code
  role: implementation
  target: src/pages/api/submission/create.ts
---

# A talent submits to a listing once

A second submission to the same listing is refused; the talent edits the one they have.
