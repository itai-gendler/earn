---
kind: primary
routes:
  web: Web
steps:
- text: The Team member publishes a Listing they unpublished earlier
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product makes it live again without verification
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    from: Unpublished
    to: Published
    facts:
    - Slug
    - Private
    - Pro only
    - Agent access
    - Foundation paying
    - Region
    - Published at
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Republish an unpublished listing

## Trigger

A sponsor brings back a listing.

## Outcome

The listing is live again.
