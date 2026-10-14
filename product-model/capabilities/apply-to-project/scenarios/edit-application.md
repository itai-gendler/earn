---
kind: primary
routes:
  web: Web
steps:
- text: The Talent chooses Edit Application before the deadline and changes their answers or quote
  kind: actor
  actor: talent
  entities:
  - entity: submission
    effect: reads
    facts:
    - Eligibility answers
    - Quote
    - Telegram
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product saves the changes and asks for a fresh AI assessment
  kind: product
  actor: talent
  entities:
  - entity: submission
    effect: changes
    facts:
    - Eligibility answers
    - Quote
    - Telegram
    - Anything else
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Edit an application

## Trigger

A talent improves their application.

## Outcome

The application shows the new answers.

## Edge cases

- A rejected application can no longer be edited.
