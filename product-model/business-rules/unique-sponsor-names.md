---
appliesTo:
- type: entity
  id: sponsor
  facts:
  - Name
  - Slug
- type: capability
  id: create-sponsor
- type: capability
  id: edit-sponsor-profile
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsors/check-name.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsors/check-slug.ts
---

# Sponsor names and page addresses are unique

Two sponsors never share a name or a page address.
