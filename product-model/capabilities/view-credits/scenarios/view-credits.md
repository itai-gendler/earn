---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens Credits
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Credit balance
    - Referral code
  contexts:
    web:
      place: earn-web::signed-in::credits
- text: The Product lists every Credit entry with its kind, change and month
  kind: product
  actor: talent
  entities:
  - entity: credit-entry
    effect: reads
    facts:
    - Kind
    - Change
    - Month
    - Dispute decision
  contexts:
    web:
      place: earn-web::signed-in::credits
---

# View credits

## Trigger

A talent checks how many submissions they have left.

## Outcome

The talent sees their balance and why it changed.
