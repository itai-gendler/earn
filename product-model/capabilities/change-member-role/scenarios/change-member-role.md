---
kind: primary
routes:
  web: Web
steps:
- text: The Admin Team member changes another member's role
  kind: actor
  actor: team-member
  entities:
  - entity: membership
    effect: reads
    facts:
    - Role
  contexts:
    web:
      place: earn-web::signed-in::team-settings
- text: The Product saves the new role
  kind: product
  actor: team-member
  entities:
  - entity: membership
    effect: changes
    facts:
    - Role
  contexts:
    web:
      place: earn-web::signed-in::team-settings
---

# Change a member role

## Trigger

A sponsor hands team management to someone else.

## Outcome

The member has the new role.
