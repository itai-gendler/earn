---
kind: edge
routes:
  web: Web
steps:
- text: The Team member starts AI Review on a bounty whose evaluation has not finished
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product refuses and changes no Submission
  kind: condition
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# AI Review before the evaluation is ready

## Trigger

The AI reviewer has not finished a bounty's entries.

## Outcome

Nothing changes; AI Review becomes available later.
