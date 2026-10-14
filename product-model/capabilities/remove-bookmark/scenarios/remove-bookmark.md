---
kind: primary
routes:
  web: Web
steps:
- text: The Talent removes the bookmark on a Listing
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
- text: The Product takes it out of the Talent's bookmarks
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: changes
    facts:
    - Bookmarked listings
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Remove a bookmark

## Trigger

A talent is no longer interested.

## Outcome

The listing is no longer in their Bookmarks.
