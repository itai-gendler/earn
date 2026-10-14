---
appliesTo:
- type: entity
  id: submission
- type: capability
  id: change-submission-label
- type: capability
  id: reject-application
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/update-label.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/reject.ts
---

# Bulk review acts on at most fifty submissions of one listing

Bulk labelling only shortlists or marks spam; bulk winner and rejection changes also stay within one listing and fifty submissions.
