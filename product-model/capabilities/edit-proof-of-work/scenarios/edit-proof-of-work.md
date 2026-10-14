---
kind: primary
routes:
  web: Web
steps:
- text: The Talent changes a Proof of Work and saves the profile
  kind: actor
  actor: talent
  entities:
  - entity: proof-of-work
    effect: reads
    facts:
    - Title
    - Description
    - Link
    - Skills
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
- text: The Product saves the change
  kind: product
  actor: talent
  entities:
  - entity: proof-of-work
    effect: changes
    facts:
    - Title
    - Description
    - Link
    - Skills
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
---

# Edit Proof of Work

## Trigger

A talent corrects a past project.

## Outcome

The profile shows the corrected project.
