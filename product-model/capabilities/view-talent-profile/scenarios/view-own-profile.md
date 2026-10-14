---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens their own profile
  kind: actor
  actor: talent
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
      place: earn-web::signed-in::talent-profile
- text: The Product shows their Proof of Work and offers Edit Profile and Share
  kind: product
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
      place: earn-web::signed-in::talent-profile
---

# View your own profile

## Trigger

A talent checks how others see them.

## Outcome

The talent sees their public profile.
