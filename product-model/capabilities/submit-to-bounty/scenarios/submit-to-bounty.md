---
kind: primary
routes:
  web: Web
steps:
- text: The Talent chooses Submit Now on an open bounty
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Deadline
    - Eligibility questions
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Talent enters the link to their work, an optional X post, any notes and the eligibility answers
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product creates the Submission and charges one credit to this month
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
- text: The Product emails the Talent a confirmation
  kind: product
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Submit to a bounty

## Trigger

A talent has done the work a bounty asks for.

## Outcome

The talent has a pending submission and one credit fewer this month.

## Edge cases

- A hackathon track takes a submission without charging a credit.
