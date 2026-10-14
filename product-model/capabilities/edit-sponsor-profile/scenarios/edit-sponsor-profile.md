---
kind: primary
routes:
  web: Web
steps:
- text: The Team member changes the sponsor's details and saves
  kind: actor
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
    - Slug
    - Logo
    - Website
    - Industry
    - X handle
    - Bio
    - Entity name
    - Location
  contexts:
    web:
      place: earn-web::signed-in::sponsor-profile
- text: The Product saves the Sponsor
  kind: product
  actor: team-member
  entities:
  - entity: sponsor
    effect: changes
    facts:
    - Name
    - Slug
    - Logo
    - Website
    - Industry
    - X handle
    - Bio
    - Entity name
    - Location
  contexts:
    web:
      place: earn-web::signed-in::sponsor-profile
---

# Edit the sponsor profile

## Trigger

A sponsor's details change.

## Outcome

The sponsor page shows the new details.
