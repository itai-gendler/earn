---
kind: primary
routes:
  web: Web
steps:
- text: The Talent disputes a spam penalty from the last seven days and explains why
  kind: actor
  actor: talent
  entities:
  - entity: credit-entry
    as: penalty
    effect: reads
    facts:
    - Kind
    - Month
  contexts:
    web:
      place: earn-web::signed-in::credits
- text: The Product records a pending dispute and passes it to the Earn team
  kind: product
  actor: talent
  entities:
  - entity: credit-entry
    as: dispute
    effect: creates
    facts:
    - Kind
    - Change
    - Month
    - Dispute decision
  contexts:
    web:
      place: earn-web::signed-in::credits
---

# Dispute a spam penalty

## Trigger

A talent thinks their work was wrongly marked as spam.

## Outcome

The dispute is pending with the Earn team.
