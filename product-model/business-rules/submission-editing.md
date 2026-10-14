---
appliesTo:
- type: entity
  id: submission
  effect: changes
  facts:
  - Link
  - Tweet link
  - Anything else
  - Eligibility answers
  - Quote
  - Telegram
permits:
- related:
  - verb: submits
    entity: talent
  when:
  - state: Pending
  - fact: Label
    is-not: Spam
- related:
  - verb: submits
    entity: talent
  when:
  - state: Winner selected
  - fact: Label
    is-not: Spam
references:
- kind: code
  role: implementation
  target: src/pages/api/submission/update.ts
---

# Talent edit only their own submission, until it is rejected or marked spam

A submission is edited by the talent who made it while it is pending or selected as a winner.
