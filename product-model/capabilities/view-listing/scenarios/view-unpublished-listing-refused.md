---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens the link of a Listing that is not live
  kind: actor
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::public::listing
- text: The Product finds no live Listing at that address
  kind: condition
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::public::listing
---

# Unpublished listing not found

## Trigger

Someone follows a link to a draft or unpublished listing.

## Outcome

The page is not found.
