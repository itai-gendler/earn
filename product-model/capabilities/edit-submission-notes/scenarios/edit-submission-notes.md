---
kind: primary
routes:
  web: Web
steps:
- text: The Team member writes notes on a Submission
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Notes
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product saves the notes
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    facts:
    - Notes
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Edit submission notes

## Trigger

A sponsor records its thinking.

## Outcome

The team sees the notes; talent never do.
