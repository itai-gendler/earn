---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens Bookmarks
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::bookmarks
- text: The Product lists every Listing the Talent saved
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Bookmarked listings
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
    - Deadline
    - Reward amount
    - Reward token
    - Status
  contexts:
    web:
      place: earn-web::signed-in::bookmarks
---

# Browse bookmarked listings

## Trigger

A talent returns to listings they saved.

## Outcome

The talent sees their saved listings with their current status.
