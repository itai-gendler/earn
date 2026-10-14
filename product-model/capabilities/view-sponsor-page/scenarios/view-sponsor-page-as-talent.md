---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens a Sponsor page
  kind: actor
  actor: talent
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
      place: earn-web::signed-in::sponsor-page
- text: The Product lists the public Listing entries of the Sponsor
  kind: product
  actor: talent
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
      place: earn-web::signed-in::sponsor-page
---

# View a sponsor page as talent

## Trigger

A talent researches a sponsor.

## Outcome

The talent sees the sponsor's details and listings.
