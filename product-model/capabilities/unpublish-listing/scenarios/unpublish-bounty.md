---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Unpublish on a live bounty Listing
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
- text: The Product takes the Listing down, clears any selected winners and refunds next month the credit each Submission cost
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
    from: Winner selected
    to: Pending
    facts:
    - Winner position
  - entity: credit-entry
    effect: creates
    facts:
    - Kind
    - Change
    - Month
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product removes the Listing from its channels
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Unpublish a bounty

## Trigger

A sponsor pulls a bounty.

## Outcome

The listing is no longer live and every submitter gets a credit back.
