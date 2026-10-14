---
kind: primary
routes:
  web: Web
steps:
- text: The Team member changes a live Listing before its deadline and chooses Update
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Description
    - Rewards
    - Deadline
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product saves the changes
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    facts:
    - Title
    - Description
    - Skills
    - Rewards
    - Reward amount
    - Eligibility questions
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Update a live listing

## Trigger

A sponsor clarifies a live listing.

## Outcome

Talent see the updated listing.
