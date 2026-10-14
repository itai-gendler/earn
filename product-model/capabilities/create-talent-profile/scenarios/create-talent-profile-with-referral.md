---
kind: primary
routes:
  web: Web
steps:
- text: The Talent creates their profile with the referral code of another Talent
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::talent-onboarding
- text: The Product saves the profile and records who referred the Talent
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
    - Referred by
  - entity: account
    effect: changes
    facts:
    - Email preferences
  contexts:
    web:
      place: earn-web::signed-in::talent-onboarding
---

# Create a talent profile with a referral code

## Trigger

A person joins through a friend.

## Outcome

The new talent is linked to the person who referred them, for referral bonuses.

## Decision points

### Referral cap

Has the referrer already brought in ten people?

- fewer than ten → the referral is recorded
- ten or more → the code is ignored and the profile is saved without it
