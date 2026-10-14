---
kind: primary
routes:
  web: Web
steps:
- text: The Team member enters the transaction link for each winner paid outside Earn
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Winner position
    - Payments
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product verifies each transaction on chain and records those that match, marking the winners paid
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    from: Won
    to: Paid
    facts:
    - Payments
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Verify an external payment

## Trigger

A sponsor paid winners from elsewhere.

## Outcome

The verified payments are recorded; any that fail are reported.
