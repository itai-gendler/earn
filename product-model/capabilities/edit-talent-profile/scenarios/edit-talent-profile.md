---
kind: primary
routes:
  web: Web
steps:
- text: The Talent changes their bio, skills, socials or work details and saves
  kind: actor
  actor: talent
  entities:
  - entity: talent
    effect: reads
    facts:
    - Bio
    - Skills
    - Socials
    - Work details
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
- text: The Product saves the profile
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: changes
    facts:
    - Bio
    - Skills
    - Socials
    - Work details
    - Interests
    - Private profile
  contexts:
    web:
      place: earn-web::signed-in::edit-profile
---

# Edit a talent profile

## Trigger

A talent keeps their profile current.

## Outcome

The profile shows the new details.
