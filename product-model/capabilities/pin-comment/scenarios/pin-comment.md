---
kind: primary
routes:
  web: Web
steps:
- text: The Team member who is point of contact pins a Comment on their Listing
  kind: actor
  actor: team-member
  entities:
  - entity: comment
    effect: reads
    facts:
    - Message
  - entity: listing
    effect: reads
    facts:
    - Point of contact
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product pins it to the top of the discussion
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

# Pin a comment

## Trigger

A sponsor wants an answer everyone sees first.

## Outcome

The comment is shown first.
