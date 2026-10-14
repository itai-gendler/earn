---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens the results of a Listing whose winners are announced
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Rewards
    - Winners announced at
  contexts:
    web:
      place: earn-web::signed-in::listing-submissions
- text: The Product lists the winners by position, then every other Submission
  kind: product
  actor: talent
  entities:
  - entity: submission
    effect: reads
    facts:
    - Link
    - Winner position
    - Reward in USD
  contexts:
    web:
      place: earn-web::signed-in::listing-submissions
---

# View results as talent

## Trigger

A talent checks the results of a listing.

## Outcome

The talent sees the winners and the work submitted.
