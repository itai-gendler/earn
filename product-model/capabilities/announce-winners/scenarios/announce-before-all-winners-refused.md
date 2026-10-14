---
kind: validation
routes:
  web: Web
steps:
- text: The Team member chooses Publish Results while podium places are still empty
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Rewards
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product refuses until every podium place is filled
  kind: condition
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Winner position
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Announcing with places unfilled

## Trigger

A sponsor tries to publish early.

## Outcome

No results are published.

## Edge cases

- Unfilled bonus spots do not block the announcement when no other submissions remain.
- Results are announced once; a second attempt is refused.
