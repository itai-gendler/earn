---
kind: edge
routes:
  web: Web
steps:
- text: The Team member proceeds while the language model fails to return some parts
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product opens the builder with the parts it received and saves a draft Listing
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: creates
    to: Draft
    facts:
    - Title
    - Type
    - Slug
    - Description
    - Point of contact
    - Region
    - Private
    - Pro only
    - Agent access
    - Foundation paying
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Auto-generate when the model fails

## Trigger

The language model is unavailable for part of the request.

## Outcome

The draft lacks the missing parts, for the team member to fill in.
