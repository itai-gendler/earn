---
kind: primary
routes:
  web: Web
steps:
- text: The Team member connects a Solana wallet and chooses Pay for a winning Submission
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Winner position
    - Reward in USD
  - entity: talent
    effect: reads
    facts:
    - Wallet address
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Team member approves the transfer of the reward to the wallet of the Talent
  kind: actor
  actor: team-member
  entities:
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product checks on chain that the transfer went to that wallet in the reward token for the reward, records it, marks the Submission paid and emails the Talent
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    from: Won
    to: Paid
    facts:
    - Payments
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Pay a bounty winner

## Trigger

A sponsor pays a bounty winner.

## Outcome

The winner is paid and the listing moves toward Completed.
