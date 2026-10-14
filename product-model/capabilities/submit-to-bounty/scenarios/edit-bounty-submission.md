---
kind: primary
routes:
  web: Web
steps:
- text: The Talent chooses Edit Submission before the deadline and changes their entry
  kind: actor
  actor: talent
  entities:
  - entity: submission
    effect: reads
    facts:
    - Link
    - Tweet link
    - Anything else
    - Eligibility answers
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product saves the changes
  kind: product
  actor: talent
  entities:
  - entity: submission
    effect: changes
    facts:
    - Link
    - Tweet link
    - Anything else
    - Eligibility answers
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Edit a bounty submission

## Trigger

A talent improves their entry.

## Outcome

The submission shows the new work; no credit is charged.

## Edge cases

- A Submission labelled Spam can no longer be edited.
