---
kind: primary
routes:
  web: Web
steps:
- text: The Team member opens My Listings
  kind: actor
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
    - Logo
    - Total rewarded
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product lists every Listing of the Sponsor with its status, submissions and payments
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
    - Status
    - Deadline
    - Reward amount
    - Reward token
    - Submission count
    - Payments made
  - entity: sponsor
    effect: reads
    facts: []
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Browse sponsor listings

## Trigger

A sponsor checks on its listings.

## Outcome

The team member sees where each listing stands and what to do next.
