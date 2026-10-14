---
appliesTo:
- type: entity
  id: submission
  facts:
  - AI review
- type: capability
  id: run-ai-review
references:
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/submissions/ai/commit-reviewed/route.ts
---

# AI suggestions change nothing until a team member runs AI Review

Earn's AI reviewer prepares a label and a note for each submission in the background; they reach the submission's label and notes only when a team member runs AI Review, and only for submissions still unreviewed.
