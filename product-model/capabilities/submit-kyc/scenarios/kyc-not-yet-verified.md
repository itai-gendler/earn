---
kind: edge
routes:
  web: Web
steps:
- text: The Talent returns before the identity check has passed
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product finds the check still open and records nothing
  kind: condition
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - KYC verified
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# KYC not yet verified

## Trigger

Identity verification is still in progress.

## Outcome

The talent is asked to finish verification; no payment is requested.
