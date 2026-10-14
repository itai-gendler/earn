---
kind: primary
routes:
  web: Web
steps:
- text: The Talent picks the For You category
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::listings
- text: The Product lists open Listing entries that need the Talent's skills, that the Talent saved, or that are featured
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Skills
    - Bookmarked listings
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
    - Logo
    - Verified
  contexts:
    web:
      place: earn-web::signed-in::listings
---

# Browse listings for you

## Trigger

A signed-in talent wants listings suited to them.

## Outcome

The talent sees open listings that need their skills, their saved listings and featured listings.
