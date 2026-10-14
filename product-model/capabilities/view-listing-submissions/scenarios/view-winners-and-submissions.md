---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the results of a Listing whose winners are announced
  kind: actor
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Rewards
    - Winners announced at
  contexts:
    web:
      place: earn-web::public::listing-submissions
- text: The Product lists the winners by position, then every other Submission with its Talent
  kind: product
  actor: visitor
  entities:
  - entity: submission
    effect: reads
    facts:
    - Link
    - Winner position
    - Reward in USD
  - entity: talent
    effect: reads
    facts:
    - Name
    - Username
    - Photo
  contexts:
    web:
      place: earn-web::public::listing-submissions
---

# View winners and submissions

## Trigger

A visitor wants to see who won.

## Outcome

The visitor sees each winner, their reward and the submitted work.
