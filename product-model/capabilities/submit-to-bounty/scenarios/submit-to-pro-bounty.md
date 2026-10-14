---
kind: primary
routes:
  web: Web
steps:
- text: The Pro Talent submits to a Pro only bounty
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Pro only
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product creates the Submission without charging a credit
  kind: product
  actor: talent
  entities:
  - entity: submission
    effect: creates
    to: Pending
    facts:
    - Link
    - Tweet link
    - Anything else
    - Eligibility answers
    - Label
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Submit to a Pro only bounty

## Trigger

A Pro member enters a Pro only bounty.

## Outcome

The talent has a pending submission; their credits are untouched.
