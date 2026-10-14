---
kind: validation
routes:
  web: Web
steps:
- text: The Team member tries to update a Listing whose deadline has passed
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Deadline
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product refuses the update
  kind: condition
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Superteam chapter
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Editing after the deadline

## Trigger

A sponsor tries to change a listing in review.

## Outcome

The listing stays as it was.

## Edge cases

- A Superteam chapter may still edit until winners are announced, but cannot widen the region to Global.
- A God Mode user may edit at any time.
