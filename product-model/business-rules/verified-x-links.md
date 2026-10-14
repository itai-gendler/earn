---
appliesTo:
- type: entity
  id: talent
  facts:
  - Verified X handles
- type: capability
  id: submit-to-bounty
- type: capability
  id: apply-to-project
- type: capability
  id: verify-x-account
references:
- kind: code
  role: implementation
  target: src/features/listings/utils/submissionFormSchema.ts
- kind: code
  role: implementation
  target: src/features/social/utils/x-verification.ts
---

# X links in a submission come from handles the talent verified

A link to an X post in a submission is accepted only when its handle is one of the talent's verified X handles.
