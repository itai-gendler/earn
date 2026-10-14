---
kind: validation
routes:
  web: Web
steps:
- text: The Talent quotes below the lowest or above the highest amount the project allows
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Quote range
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product refuses the application
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

# Quote outside the range

## Trigger

A quote does not fit the range.

## Outcome

Nothing is submitted until the quote is within the range.
