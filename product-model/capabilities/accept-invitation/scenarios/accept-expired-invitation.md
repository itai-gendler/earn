---
kind: edge
routes:
  web: Web
steps:
- text: The Team member opens an Invitation more than seven days old
  kind: actor
  actor: team-member
  entities:
  - entity: invitation
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::invitation
- text: The Product finds the Invitation expired and sends them to onboarding instead
  kind: condition
  actor: team-member
  entities:
  - entity: invitation
    effect: reads
    facts:
    - Expires at
  contexts:
    web:
      place: earn-web::signed-in::invitation
---

# Expired invitation

## Trigger

An invitation was left too long.

## Outcome

They do not join; an Admin can invite them again.
