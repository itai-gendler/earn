---
kind: primary
routes:
  web: Web
steps:
- text: The Team member opens the preview of a Listing that is not yet live
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product shows the Listing because it belongs to the Team member's sponsor
  kind: product
  actor: team-member
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
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Preview a draft listing

## Trigger

A team member checks how a listing will look.

## Outcome

The team member sees the listing page before it goes live.
