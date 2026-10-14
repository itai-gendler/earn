---
kind: validation
routes:
  web: Web
steps:
- text: The Team member chooses Publish while rewards do not add up to the total or the deadline is in the past
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Rewards
    - Reward amount
    - Deadline
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product refuses and points to the fields to fix
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

# Publishing an incomplete listing

## Trigger

A listing is not ready.

## Outcome

The listing stays a draft.
