---
appliesTo:
- type: entity
  id: listing
  effect: reads
permits:
- actors:
  - visitor
  - talent
  when:
  - state: Published
- actors:
  - visitor
  - talent
  when:
  - state: Winners Announced
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
  target: src/pages/api/listings/details/[slug].ts
- kind: code
  role: implementation
  target: src/pages/earn/listing/[slug]/index.tsx
---

# Only the sponsor's team and God Mode users see a listing that is not live

Anyone sees a published listing or one whose winners are announced. Drafts, listings under verification and unpublished listings are seen only by the sponsor's team, in the dashboard and in preview.
