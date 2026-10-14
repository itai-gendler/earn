---
kind: primary
routes:
  web: Web
steps:
- text: The Talent chooses Add Project and enters the title, description, link and skills
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
- text: The Product adds the Proof of Work to the profile
  kind: product
  actor: talent
  entities:
  - entity: proof-of-work
    effect: creates
    facts:
    - Title
    - Description
    - Link
    - Skills
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
---

# Add Proof of Work

## Trigger

A talent wants to show earlier work.

## Outcome

The project appears under Proof of Work on their profile.
