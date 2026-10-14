---
kind: primary
routes:
  web: Web
steps:
- text: The Talent bookmarks a Listing
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
- text: The Product adds it to the Talent's bookmarks
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

# Bookmark a listing

## Trigger

A talent wants to come back to a listing.

## Outcome

The listing is in their Bookmarks.
