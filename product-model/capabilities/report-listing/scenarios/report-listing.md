---
kind: primary
routes:
  web: Web
steps:
- text: The Talent reports a Listing, picking a reason and adding details
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product passes the report to the Earn team with the email of the Talent
  kind: product
  actor: talent
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Report a listing

## Trigger

A talent thinks something is wrong with a listing.

## Outcome

The Earn team receives the report; Earn keeps no record of it.
