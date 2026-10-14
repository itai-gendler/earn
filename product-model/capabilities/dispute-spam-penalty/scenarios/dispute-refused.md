---
kind: validation
routes:
  web: Web
steps:
- text: The Talent disputes a penalty older than seven days or already disputed
  kind: actor
  actor: talent
  entities:
  - entity: credit-entry
    effect: reads
    facts:
    - Kind
    - Month
  contexts:
    web:
      place: earn-web::signed-in::credits
- text: The Product refuses the dispute
  kind: condition
  actor: talent
  entities:
  - entity: credit-entry
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::credits
---

# Dispute refused

## Trigger

A dispute comes too late or twice.

## Outcome

No dispute is recorded.
