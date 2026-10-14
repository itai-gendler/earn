---
appliesTo:
- type: entity
  id: submission
  effect: changes
  facts:
  - Label
  - Notes
  - AI review
permits:
- related:
  - verb: receives
    entity: listing
  - verb: posts
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
- actors:
  - god-mode-user
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/update-label.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/update-notes.ts
---

# Members of the listing's sponsor and God Mode users label and annotate its submissions

Labels, notes and AI Review results are the sponsor team's own; talent never see notes.
