---
kind: primary
routes:
  web: Web
steps:
- text: The Team member moves the deadline of a live Listing later, by at most two weeks
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
- text: The Product saves the deadline, posts a deadline Comment on the Listing and sends a deadline email about it
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    facts:
    - Deadline
  - entity: comment
    effect: creates
    facts:
    - Message
    - Pinned
    - Kind
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Extend the deadline

## Trigger

A sponsor gives talent more time.

## Outcome

Everyone following the listing knows the new deadline.
