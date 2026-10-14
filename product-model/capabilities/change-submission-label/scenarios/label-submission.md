---
kind: primary
routes:
  web: Web
steps:
- text: The Team member picks a label for a Submission
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Label
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product saves the label
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    facts:
    - Label
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Label a submission

## Trigger

A sponsor sorts entries.

## Outcome

The submission carries the label.
