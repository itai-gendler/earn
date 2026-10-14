---
appliesTo:
- type: entity
  id: talent
  facts:
  - Location
- type: capability
  id: submit-to-bounty
- type: capability
  id: apply-to-project
references:
- kind: code
  role: implementation
  target: src/features/listings/utils/region.ts
- kind: code
  role: implementation
  target: src/features/listings/utils/locationCooldown.ts
---

# Regional listings take submissions only from talent located in the region

A listing with a region other than Global takes submissions only from talent whose profile location is in that country or region. After a talent replaces their location, listings of the new region stay closed to them for 21 days.

## Rationale

The cooldown stops people from moving their location to enter a regional listing.
