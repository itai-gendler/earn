---
kind: primary
routes:
  web: Web
steps:
- text: The God Mode user chooses Create New Sponsor and enters its details
  kind: actor
  actor: god-mode-user
  entities:
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
- text: The Product creates the Sponsor with the God Mode user as Admin and makes it their current sponsor
  kind: product
  actor: god-mode-user
  entities:
  - entity: sponsor
    effect: creates
    facts:
    - Name
    - Slug
    - Logo
    - Website
    - Industry
    - X handle
    - Bio
    - Entity name
    - Location
    - Verified
    - Superteam chapter
  - entity: membership
    effect: creates
    facts:
    - Role
    with: sponsor
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
---

# God Mode creates another sponsor

## Trigger

The Earn team sets up a sponsor on its behalf.

## Outcome

The new sponsor exists; the God Mode user can work in its dashboard.

## Edge cases

- A Team member who already works for a sponsor is taken to My Listings instead of creating another.
