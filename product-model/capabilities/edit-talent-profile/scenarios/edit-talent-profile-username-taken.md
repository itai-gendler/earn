---
kind: validation
routes:
  web: Web
steps:
- text: The Talent changes their username to one another person holds
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Username
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
- text: The Product refuses the change
  kind: condition
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
---

# Username already taken

## Trigger

A talent picks a taken username.

## Outcome

The profile keeps its username.
