---
appliesTo:
- type: entity
  id: submission
  facts:
  - Winner position
- type: capability
  id: select-winner
- type: capability
  id: announce-winners
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/toggle-winner.ts
---

# Each podium place goes to one submission

No two submissions hold the same podium place, bonus winners never outnumber the bonus spots, and a project has exactly one winner.
