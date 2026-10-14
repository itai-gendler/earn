---
appliesTo:
- type: entity
  id: listing
  effect: changes
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
  target: src/features/auth/utils/checkListingSponsorAuth.ts
- kind: code
  role: implementation
  target: src/features/auth/utils/getSponsorSession.ts
---

# Members of the listing's sponsor and God Mode users change a listing

Every change to a listing, from editing to publishing, unpublishing and announcing winners, is made from the dashboard of the sponsor that posted it.
