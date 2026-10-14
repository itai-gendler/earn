---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor searches with keywords
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public::listings
- text: The Product lists public Listing entries whose title or sponsor name matches the words
  kind: product
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
    - Region
    - Deadline
    - Reward amount
    - Reward token
    - Compensation type
    - Status
    - Submission count
  - entity: sponsor
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: earn-web::public::listings
---

# Search listings

## Trigger

A visitor looks for a particular kind of work.

## Outcome

The visitor sees the listings that match the search.
