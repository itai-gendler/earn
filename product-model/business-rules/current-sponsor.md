---
appliesTo:
- type: entity
  id: team-member
  facts:
  - Current sponsor
- type: capability
  id: switch-sponsor
references:
- kind: code
  role: implementation
  target: src/pages/api/user/update.ts
---

# A team member works only in the dashboards of sponsors whose team they are on

God Mode users may work in any sponsor's dashboard.
