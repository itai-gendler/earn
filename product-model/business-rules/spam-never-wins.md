---
appliesTo:
- type: entity
  id: submission
  facts:
  - Label
- type: capability
  id: select-winner
- type: capability
  id: change-submission-label
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/toggle-winner.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/update-label.ts
---

# A submission marked Spam is never a winner

Marking a selected winner as Spam drops its place; selecting a Spam submission as a winner clears the Spam label.
