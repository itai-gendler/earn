---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Delete Draft on a draft Listing
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
- text: The Product deletes the draft
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: removes
    from: Draft
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Delete a draft listing

## Trigger

A sponsor abandons a draft.

## Outcome

The draft is gone from My Listings.
