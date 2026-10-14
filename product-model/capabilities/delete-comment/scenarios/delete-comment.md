---
kind: primary
routes:
  web: Web
steps:
- text: The Talent deletes their own Comment
  kind: actor
  actor: talent
  entities:
  - entity: comment
    as: own
    effect: reads
    facts:
    - Message
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product deletes the Comment and every reply to it
  kind: product
  actor: talent
  entities:
  - entity: comment
    as: own
    effect: removes
  - entity: comment
    as: reply
    effect: removes
    with: own
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Delete a comment

## Trigger

A talent takes back what they wrote.

## Outcome

The comment and its replies are gone.
