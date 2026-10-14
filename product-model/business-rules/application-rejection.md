---
appliesTo:
- type: entity
  id: submission
  effect: changes
  to: Rejected
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
  target: src/pages/api/sponsor-dashboard/submission/reject.ts
---

# Members of the listing's sponsor and God Mode users reject applications

Rejecting tells the applicant by email and ends their chance to edit the application.
