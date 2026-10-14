---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Duplicate on a Listing in My Listings
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    as: original
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product opens the builder filled from the original and saves the copy as a new draft
  kind: product
  actor: team-member
  entities:
  - entity: listing
    as: copy
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

# Duplicate a listing

## Trigger

A sponsor repeats a listing.

## Outcome

A new draft exists with the original details.
