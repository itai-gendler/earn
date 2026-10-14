---
kind: primary
routes:
  web: Web
steps:
- text: The Talent chooses Send Quote on a project that takes quotes and enters an amount
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Compensation type
    - Quote range
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product creates the Submission with the quote and charges one credit
  kind: product
  actor: talent
  entities:
  - entity: submission
    effect: creates
    to: Pending
    facts:
    - Eligibility answers
    - Telegram
    - Anything else
    - Label
    - Quote
  - entity: credit-entry
    effect: creates
    facts:
    - Kind
    - Change
    - Month
    with: submission
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Send a quote

## Trigger

A project lets applicants name their price.

## Outcome

The application carries the quote.
