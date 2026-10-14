---
kind: validation
routes:
  web: Web
steps:
- text: The Team member sends verification details for a Listing that is not under verification
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product refuses
  kind: condition
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Verification for a listing not under verification

## Trigger

Verification details arrive for the wrong listing.

## Outcome

Nothing is recorded.
