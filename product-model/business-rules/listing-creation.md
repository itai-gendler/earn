---
appliesTo:
- type: entity
  id: listing
  effect: creates
permits:
- related:
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
  target: src/app/api/sponsor-dashboard/listing/draft/route.ts
- kind: code
  role: implementation
  target: src/features/auth/utils/checkListingSponsorAuth.ts
---

# Members of a sponsor's team and God Mode users create its listings

A listing belongs to the team member's current sponsor, and the team member who starts it becomes its point of contact.
