---
kind: primary
routes:
  web: Web
steps:
- text: The Talent writes a question on a Listing
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
- text: The Product posts the Comment and emails the point of contact
  kind: product
  actor: talent
  entities:
  - entity: comment
    effect: creates
    facts:
    - Message
    - Pinned
    - Kind
  - entity: listing
    effect: reads
    facts:
    - Point of contact
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Comment on a listing

## Trigger

A talent has a question about a listing.

## Outcome

The question is public on the listing and the point of contact is told.

## Edge cases

- Everyone mentioned by username is emailed, except the writer.
