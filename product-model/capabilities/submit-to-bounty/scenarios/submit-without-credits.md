---
kind: validation
routes:
  web: Web
steps:
- text: The Talent with no credits left this month tries to submit to a bounty
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Credit balance
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product refuses and creates no Submission
  kind: condition
  actor: talent
  entities:
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Submission refused without credits

## Trigger

A talent has used all their credits.

## Outcome

Nothing is submitted; credits return at the start of next month.
