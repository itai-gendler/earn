---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Unpublish on a live project Listing
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Status
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product takes the Listing down, rejects every application, emails each applicant and refunds their credit next month
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    from: Published
    to: Unpublished
    facts: []
  - entity: submission
    effect: changes
    from: Pending
    to: Rejected
    facts: []
  - entity: credit-entry
    effect: creates
    facts:
    - Kind
    - Change
    - Month
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Unpublish a project

## Trigger

A sponsor cancels a project.

## Outcome

The listing is down and every applicant is told.
