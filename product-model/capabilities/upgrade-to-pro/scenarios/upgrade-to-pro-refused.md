---
kind: validation
routes:
  web: Web
steps:
- text: The Talent who has earned under $1,000 chooses to upgrade
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Total earned
  contexts:
    web:
      place: earn-web::signed-in::pro
- text: The Product refuses and says how much the Talent has earned so far
  kind: condition
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Total earned
    - Superteam membership
  contexts:
    web:
      place: earn-web::signed-in::pro
---

# Pro upgrade refused

## Trigger

A newer talent tries to upgrade.

## Outcome

The talent stays on the free plan.
