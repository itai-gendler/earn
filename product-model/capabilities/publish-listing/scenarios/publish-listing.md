---
kind: primary
routes:
  web: Web
steps:
- text: The Team member of a verified Sponsor sets the pre-publish options and chooses Publish
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Private
    - Pro only
    - Agent access
    - Slug
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product makes the Listing live and records its US dollar value at today's token price
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    from: Draft
    to: Published
    facts:
    - Slug
    - Private
    - Pro only
    - Agent access
    - Foundation paying
    - Region
    - USD value
    - Published at
  - entity: sponsor
    effect: reads
    facts:
    - Verified
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product announces the new Listing on Earn's community channels
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Publish a listing

## Trigger

A sponsor is ready to go live.

## Outcome

The listing is live and talent can submit.
