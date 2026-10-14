---
kind: primary
routes:
  web: Web
steps:
- text: The Team member replies to a Comment on their Listing
  kind: actor
  actor: team-member
  entities:
  - entity: comment
    as: question
    effect: reads
    facts:
    - Message
  - entity: listing
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product posts the reply and emails the author of the original Comment
  kind: product
  actor: team-member
  entities:
  - entity: comment
    as: answer
    effect: creates
    facts:
    - Message
    - Pinned
    - Kind
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Reply to a comment

## Trigger

A sponsor answers a question.

## Outcome

The reply sits under the question and its author is told.
