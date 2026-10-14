---
appliesTo:
- type: entity
  id: listing
- type: capability
  id: browse-listings
- type: capability
  id: view-sponsor-page
references:
- kind: code
  role: implementation
  target: src/features/listings/utils/query-builder.ts
---

# Private listings stay out of feeds and search

A private listing is reachable only through its link; it never appears in listing feeds, search or sponsor pages.
