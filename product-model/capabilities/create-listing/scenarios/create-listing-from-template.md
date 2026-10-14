---
kind: primary
routes:
  web: Web
steps:
- text: The Team member picks a template for the kind of work they need
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product fills the builder with the template's description, skills and rewards and saves a draft Listing
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
    - Skills
    - Region
    - Deadline
    - Reward token
    - Compensation type
    - Rewards
    - Bonus spots
    - Reward amount
    - Quote range
    - Eligibility questions
    - Point of contact
    - Private
    - Pro only
    - Agent access
    - Foundation paying
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Create a listing from a template

## Trigger

A sponsor posts a common kind of work.

## Outcome

A draft listing starts from the template.
