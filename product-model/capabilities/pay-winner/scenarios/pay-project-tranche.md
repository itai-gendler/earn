---
kind: primary
routes:
  web: Web
steps:
- text: The Team member pays the next tranche of a project winner
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Payments
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product verifies the transfer and records it as the next tranche
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    facts:
    - Payments
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Pay a project tranche

## Trigger

A sponsor pays a project in parts.

## Outcome

The tranche is recorded; the winner is paid in full once tranches reach the reward.
