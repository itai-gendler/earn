---
kind: primary
routes:
  web: Web
steps:
- text: The Admin Team member removes a member from the team
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
- text: The Product ends their place on the team and clears the Sponsor as their current sponsor
  kind: product
  actor: team-member
  entities:
  - entity: membership
    effect: removes
  - entity: team-member
    as: removed-member
    effect: changes
    facts:
    - Current sponsor
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::team-settings
---

# Remove a team member

## Trigger

Someone leaves the sponsor.

## Outcome

The person no longer works in the sponsor's dashboard.
