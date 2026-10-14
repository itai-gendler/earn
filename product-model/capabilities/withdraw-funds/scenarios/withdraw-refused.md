---
kind: validation
routes:
  web: Web
steps:
- text: The Talent enters an invalid address or an amount too small to send
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::wallet
- text: The Product refuses and sends nothing
  kind: condition
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::wallet
---

# Withdrawal refused

## Trigger

A withdrawal cannot go through.

## Outcome

No tokens move.

## Edge cases

- Cancelling in the confirmation, or failing two-factor verification, sends nothing.
