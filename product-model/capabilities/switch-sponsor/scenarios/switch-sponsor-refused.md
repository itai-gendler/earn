---
kind: validation
routes:
  web: Web
steps:
- text: The Team member asks to switch to a Sponsor whose team they are not on
  kind: actor
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product refuses
  kind: condition
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Switching to a sponsor you do not belong to

## Trigger

Someone tries to open another sponsor.

## Outcome

The current sponsor stays the same.
