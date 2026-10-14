---
appliesTo:
- type: entity
  id: submission
- type: capability
  id: view-listing-submissions
references:
- kind: code
  role: implementation
  target: src/pages/api/listings/submissions/[slug].ts
---

# A listing's submissions are public only once its winners are announced

Before the announcement only the submission count is public; the sponsor's team sees every submission in its dashboard and each talent sees their own.
