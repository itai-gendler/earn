---
kind: validation
routes:
  web: Web
steps:
- text: The Admin Team member tries to change their own role
  kind: actor
  actor: team-member
  entities:
  - entity: membership
    effect: reads
    facts:
    - Role
  contexts:
    web:
      place: earn-web::signed-in::team-settings
- text: The Product refuses
  kind: condition
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::team-settings
---

# Changing your own role

## Trigger

An Admin tries to demote themselves.

## Outcome

Their role stays the same.
