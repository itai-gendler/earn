---
kind: validation
routes:
  web: Web
steps:
- text: The Team member records a transfer to another wallet, in another token, for another amount, or already recorded
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
- text: The Product refuses to record it
  kind: condition
  actor: team-member
  entities:
  - entity: talent
    effect: reads
    facts:
    - Wallet address
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Payment that does not match

## Trigger

A transfer does not match the reward.

## Outcome

Nothing is recorded.

## Edge cases

- A bounty winner is paid in one payment.
