---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens a Listing
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
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
    - Point of contact
    - Pro only
    - Agent access
    - Status
    - Submission count
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: 'The Product shows whether the Talent may submit: region, Pro, credits and deadline'
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Location
    - Pro
    - Credit balance
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# View a listing as talent

## Trigger

A talent considers submitting.

## Outcome

The talent sees the listing and whether they can take part now.

## Edge cases

- A Talent who already submitted sees their Submission and may edit it until the deadline.
