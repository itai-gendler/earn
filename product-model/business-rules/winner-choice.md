---
appliesTo:
- type: entity
  id: submission
  effect: changes
  facts:
  - Winner position
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
  target: src/pages/api/sponsor-dashboard/submission/toggle-winner.ts
---

# Members of the listing's sponsor and God Mode users choose its winners

Winner places are given and taken back from the dashboard of the sponsor that posted the listing.
