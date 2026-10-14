---
kind: primary
routes:
  web: Web
steps:
- text: The Team member opens the dashboard of a Sponsor without an entity name
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
- text: The Team member enters the legal entity name the dashboard asks for
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product saves the entity name
  kind: product
  actor: team-member
  entities:
  - entity: sponsor
    effect: changes
    facts:
    - Entity name
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Add the entity name

## Trigger

A sponsor created before entity names were asked for.

## Outcome

The sponsor has an entity name and the dashboard stops asking.
