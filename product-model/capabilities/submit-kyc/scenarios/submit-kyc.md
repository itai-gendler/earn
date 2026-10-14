---
kind: primary
routes:
  web: Web
steps:
- text: The Talent who won a foundation-paid Listing chooses Submit KYC and completes identity verification
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product confirms the verification passed, records it and asks Superteam to pay every unpaid foundation-paid win
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: changes
    facts:
    - KYC verified
  - entity: submission
    effect: reads
    facts:
    - Winner position
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Submit KYC

## Trigger

A winner of a foundation-paid listing is asked for KYC.

## Outcome

The talent's payment is being processed by Superteam.
