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
  target: src/features/listings/utils/validateSubmissionRequest.ts
- kind: code
  role: implementation
  target: src/features/listings/utils/deadline.ts
---

# Submissions are taken and edited only until the deadline

After the deadline a listing takes no new submissions and existing ones can no longer be edited.
