---
kind: validation
routes:
  web: Web
steps:
- text: The Team member invites an eleventh Scout to the same Listing
  kind: actor
  actor: team-member
  entities:
  - entity: scout
    effect: reads
    facts:
    - Invited
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product refuses
  kind: condition
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Scout invitation limit reached

## Trigger

A sponsor has used all its scout invitations.

## Outcome

No more invitations are sent.
