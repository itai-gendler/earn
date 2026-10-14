---
kind: primary
routes:
  web: Web
steps:
- text: The Admin Team member enters an email address and a role
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::team-settings
- text: The Product creates an Invitation valid for seven days and emails its link
  kind: product
  actor: team-member
  entities:
  - entity: invitation
    effect: creates
    facts:
    - Email
    - Role
    - Expires at
  contexts:
    web:
      place: earn-web::signed-in::team-settings
---

# Invite a team member

## Trigger

A sponsor grows its team.

## Outcome

The person receives an invitation to join.
