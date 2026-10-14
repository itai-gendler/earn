---
kind: primary
routes:
  web: Web
steps:
- text: The Team member gives the Superteam chapter and lead who know the Sponsor
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product records the details and asks the chapter lead and the Earn team to verify the Listing
  kind: product
  actor: team-member
  entities:
  - entity: sponsor
    effect: changes
    facts:
    - Verification details
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Submit sponsor verification

## Trigger

A listing is under verification.

## Outcome

The Earn team has what it needs to verify the sponsor.
