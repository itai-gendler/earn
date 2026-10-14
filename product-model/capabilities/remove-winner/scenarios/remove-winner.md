---
kind: primary
routes:
  web: Web
steps:
- text: The Team member removes the place of a Submission
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
- text: The Product frees the place
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    from: Winner selected
    to: Pending
    facts:
    - Winner position
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Remove a winner

## Trigger

A sponsor changes its mind.

## Outcome

The place is free for another submission.
