---
kind: validation
routes:
  web: Web
steps:
- text: The Admin Team member invites an address the Earn team has blocked
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::team-settings
- text: The Product refuses and sends no Invitation
  kind: condition
  actor: team-member
  entities:
  - entity: invitation
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::team-settings
---

# Invitation to a blocked address

## Trigger

A sponsor invites a blocked address.

## Outcome

Nothing is sent.
