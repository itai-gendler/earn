---
kind: validation
routes:
  web: Web
steps:
- text: The Team member enters payments for a Listing whose winners are not announced
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Status
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product refuses
  kind: condition
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Verifying before the announcement

## Trigger

A sponsor pays before announcing.

## Outcome

Nothing is recorded.
