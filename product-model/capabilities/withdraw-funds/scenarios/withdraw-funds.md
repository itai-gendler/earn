---
kind: primary
routes:
  web: Web
steps:
- text: The Talent picks a token, enters an amount and a Solana address and confirms with two-factor verification
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
- text: The Product prepares the transfer, paying the network fee and charging the cost of a new token holding at the address in the token itself
  kind: product
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::wallet
- text: The Product sends the transfer and shows it in the wallet activity
  kind: product
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::wallet
---

# Withdraw funds

## Trigger

A talent moves their earnings out.

## Outcome

The tokens arrive at the address.
