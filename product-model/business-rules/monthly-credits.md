---
appliesTo:
- type: entity
  id: credit-entry
- type: capability
  id: submit-to-bounty
- type: capability
  id: apply-to-project
- type: capability
  id: view-credits
references:
- kind: code
  role: implementation
  target: src/features/credits/utils/creditAggregate.ts
- kind: code
  role: implementation
  target: src/features/credits/utils/canUserSubmit.ts
---

# Talent have three submission credits a month, four with Pro

Each submission to a bounty or project costs one credit from the current month. Pro only listings and hackathon tracks cost none. A talent with no credits left cannot submit until the month turns.
