---
kind: primary
routes:
  web: Web
steps:
- text: The Talent removes a Proof of Work and saves the profile
  kind: actor
  actor: talent
  entities:
  - entity: proof-of-work
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
- text: The Product deletes it
  kind: product
  actor: talent
  entities:
  - entity: proof-of-work
    effect: removes
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
---

# Delete Proof of Work

## Trigger

A talent no longer wants to show a project.

## Outcome

The project is gone from the profile.
