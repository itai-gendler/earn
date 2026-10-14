---
kind: validation
routes:
  web: Web
steps:
- text: The Team member picks a place another Submission holds, or a bonus spot beyond the number offered
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
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
    facts:
    - Bonus spots
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Place already taken

## Trigger

Two submissions compete for one place.

## Outcome

The place stays with the first.

## Edge cases

- After the results are announced no winner can be changed.
