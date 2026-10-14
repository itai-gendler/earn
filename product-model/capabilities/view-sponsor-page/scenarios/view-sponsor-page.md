---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens a Sponsor page
  kind: actor
  actor: visitor
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
    - Logo
    - Bio
    - Website
    - X handle
    - Industry
    - Verified
    - Total rewarded
  contexts:
    web:
      place: earn-web::public::sponsor-page
- text: The Product lists the public Listing entries of the Sponsor
  kind: product
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
    - Deadline
    - Reward amount
    - Reward token
    - Status
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::public::sponsor-page
---

# View a sponsor page

## Trigger

A visitor wants to know who is behind a listing.

## Outcome

The visitor sees the sponsor's details and listings.
