---
kind: validation
routes:
  web: Web
steps:
- text: The Team member tries to pin a reply
  kind: actor
  actor: team-member
  entities:
  - entity: comment
    effect: reads
    facts:
    - Message
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product refuses because only a top-level Comment can be pinned
  kind: condition
  actor: team-member
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Replies cannot be pinned

## Trigger

A sponsor tries to pin a reply.

## Outcome

Nothing is pinned.
