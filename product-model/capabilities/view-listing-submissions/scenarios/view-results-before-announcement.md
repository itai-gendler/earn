---
kind: edge
routes:
  web: Web
steps:
- text: The Visitor opens the results of a Listing whose winners are not announced
  kind: actor
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::public::listing-submissions
- text: The Product shows no Submission
  kind: product
  actor: visitor
  entities:
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::public::listing-submissions
---

# Results before the announcement

## Trigger

A visitor looks at results too early.

## Outcome

No submissions are shown until the winners are announced.
