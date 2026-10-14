---
kind: primary
routes:
  web: Web
steps:
- text: The Talent enters a username, name, photo, location, skills, socials and work details
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::talent-onboarding
- text: The Product saves the profile, creates an Earn wallet and a referral code, and turns on the talent email preferences
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: changes
    facts:
    - Username
    - Name
    - Photo
    - Location
    - Skills
    - Socials
    - Work details
    - Interests
    - Profile complete
    - Wallet address
    - Referral code
  - entity: account
    effect: changes
    facts:
    - Email preferences
  contexts:
    web:
      place: earn-web::signed-in::talent-onboarding
- text: The Product returns the Talent to the page they came from, or to the home page
  kind: product
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::talent-onboarding
---

# Create a talent profile

## Trigger

A signed-in person wants to take part as talent.

## Outcome

The person has a complete talent profile and an Earn wallet, and can submit.
