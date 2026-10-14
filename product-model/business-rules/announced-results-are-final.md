---
appliesTo:
- type: entity
  id: submission
- type: capability
  id: select-winner
- type: capability
  id: remove-winner
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

# Announced results are final

Results are announced once. After that no winner is selected or removed and the label of a winner no longer changes.
