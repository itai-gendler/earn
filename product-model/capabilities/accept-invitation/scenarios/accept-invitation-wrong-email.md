---
kind: validation
routes:
  web: Web
steps:
- text: The Team member opens an Invitation sent to a different email than the one they signed in with
  kind: actor
  actor: team-member
  entities:
  - entity: invitation
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: earn-web::signed-in::invitation
- text: The Product refuses and asks them to sign in with the invited email
  kind: condition
  actor: team-member
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: earn-web::signed-in::invitation
---

# Invitation for another email

## Trigger

Someone opens an invitation meant for another address.

## Outcome

They do not join the team.
