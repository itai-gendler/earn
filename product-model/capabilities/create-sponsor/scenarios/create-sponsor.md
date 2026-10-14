---
kind: primary
routes:
  web: Web
steps:
- text: The Team member enters a name, page address, logo, website, industry, X handle, bio, entity name and location
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
- text: The Product creates the Sponsor with the Team member as Admin, makes it their current sponsor and turns on the sponsor email preferences
  kind: product
  actor: team-member
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
  - entity: team-member
    effect: changes
    facts:
    - Current sponsor
  - entity: account
    effect: changes
    facts:
    - Email preferences
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
- text: The Product sends a welcome email and opens My Listings ready to create the first Listing
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Create a sponsor

## Trigger

A person wants to post work on Earn for their organisation.

## Outcome

The sponsor exists with the person as its Admin, and they are ready to create a listing.
