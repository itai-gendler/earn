---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens an unsubscribe link whose signature does not match the address
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public
- text: The Product refuses the request
  kind: condition
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public
---

# Unsubscribe link that does not match

## Trigger

An unsubscribe link has been altered.

## Outcome

Nothing changes.
