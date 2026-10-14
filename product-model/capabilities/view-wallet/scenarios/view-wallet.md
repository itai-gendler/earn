---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens their wallet
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Wallet address
  contexts:
    web:
      place: earn-web::signed-in::wallet
- text: The Product shows the token balances, their dollar value and recent activity of the wallet
  kind: product
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::wallet
---

# View wallet

## Trigger

A talent checks what they have been paid.

## Outcome

The talent sees their balances and incoming and outgoing transfers.
