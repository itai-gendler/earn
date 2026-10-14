---
kind: validation
routes:
  web: Web
steps:
- text: The Team member tries to change the label of a winner after the results are announced
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Label
    - Winner position
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product refuses
  kind: condition
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Labelling an announced winner

## Trigger

A sponsor revisits a winner.

## Outcome

The label stays.
