---
kind: primary
routes:
  web: Web
steps:
- text: The Talent replaces their location and confirms the cooldown warning
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Location
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
- text: The Product saves the new location and starts a 21-day cooldown for regional listings
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: changes
    facts:
    - Location
    - Location changed at
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
---

# Change location

## Trigger

A talent moves country.

## Outcome

The talent may enter listings of the new region only after the cooldown ends.
