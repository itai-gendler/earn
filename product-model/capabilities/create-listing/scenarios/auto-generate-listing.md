---
kind: primary
routes:
  web: Web
steps:
- text: The Team member describes the work in Auto Generate and proceeds
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product asks a language model for the description, title, token, skills, rewards and eligibility questions
  kind: product
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product opens the builder filled with the result and saves a draft Listing
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

# Auto-generate a listing

## Trigger

A sponsor wants a head start.

## Outcome

A draft listing exists, filled in for the team member to review.
