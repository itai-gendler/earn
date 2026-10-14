---
kind: primary
routes:
  web: Web
steps:
- text: The Team member changes a draft Listing in the builder
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Description
    - Rewards
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product saves the changes as the Team member writes
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    facts:
    - Title
    - Description
    - Skills
    - Region
    - Deadline
    - Winner announcement date
    - Reward token
    - Compensation type
    - Rewards
    - Bonus spots
    - Reward amount
    - Quote range
    - Eligibility questions
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Edit a draft listing

## Trigger

A sponsor refines a draft.

## Outcome

The draft holds the latest changes.
