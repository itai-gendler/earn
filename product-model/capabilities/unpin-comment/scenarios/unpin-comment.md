---
kind: primary
routes:
  web: Web
steps:
- text: The Team member who is point of contact unpins a pinned Comment
  kind: actor
  actor: team-member
  entities:
  - entity: comment
    effect: reads
    facts:
    - Message
    - Pinned
  - entity: listing
    effect: reads
    facts:
    - Point of contact
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product unpins it
  kind: product
  actor: team-member
  entities:
  - entity: comment
    effect: changes
    facts:
    - Pinned
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Unpin a comment

## Trigger

A pinned answer is no longer needed first.

## Outcome

The comment returns to its usual place.
