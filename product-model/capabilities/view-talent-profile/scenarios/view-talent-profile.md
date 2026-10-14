---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the profile of a Talent
  kind: actor
  actor: visitor
  entities:
  - entity: talent
    effect: reads
    facts:
    - Name
    - Username
    - Photo
    - Bio
    - Location
    - Skills
    - Socials
    - Work details
    - Pro
    - Total earned
  contexts:
    web:
      place: earn-web::public::talent-profile
- text: The Product shows the Proof of Work of the Talent
  kind: product
  actor: visitor
  entities:
  - entity: proof-of-work
    effect: reads
    facts:
    - Title
    - Description
    - Link
    - Skills
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::public::talent-profile
---

# View a talent profile

## Trigger

A visitor looks someone up.

## Outcome

The visitor sees the talent's details, earnings and past work.
