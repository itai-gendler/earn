---
kind: primary
routes:
  web: Web
steps:
- text: The Talent chooses to upgrade on the Pro page
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Pro
    - Total earned
  contexts:
    web:
      place: earn-web::signed-in::pro
- text: The Product confirms the Talent has earned at least $1,000 and makes them Pro
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: changes
    facts:
    - Pro
  contexts:
    web:
      place: earn-web::signed-in::pro
---

# Upgrade to Pro

## Trigger

An established talent wants Pro.

## Outcome

The talent is Pro from now on.

## Edge cases

- A recognised Superteam member is made Pro whatever they have earned.
