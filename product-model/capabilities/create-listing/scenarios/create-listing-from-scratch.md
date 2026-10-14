---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Create New Listing and picks a bounty or a project
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Team member starts writing the title and description in the listing builder
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product saves a draft Listing with the Team member as point of contact
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

# Create a listing from scratch

## Trigger

A sponsor has work to post.

## Outcome

A draft listing exists and keeps saving as the team member writes.
