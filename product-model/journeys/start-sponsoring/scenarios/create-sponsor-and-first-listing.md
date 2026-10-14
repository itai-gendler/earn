---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Team member enters the details of their organisation
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
  capability: create-sponsor
- text: The Product creates the Sponsor with the Team member as Admin
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
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
  capability: create-sponsor
- text: The Product opens My Listings ready to create the first Listing
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
  capability: create-sponsor
- text: The Team member picks a bounty or a project and starts writing
  kind: actor
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
  capability: create-listing
- text: The Product saves a draft Listing
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: creates
    to: Draft
    facts:
    - Title
    - Type
    - Slug
    - Description
    - Skills
    - Region
    - Deadline
    - Reward token
    - Compensation type
    - Rewards
    - Bonus spots
    - Reward amount
    - Quote range
    - Eligibility questions
    - Point of contact
    - Private
    - Pro only
    - Agent access
    - Foundation paying
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
  capability: create-listing
---

# Create a sponsor and its first listing

## Trigger

A person sets up their organisation as a sponsor.

## Outcome

The sponsor exists and its first listing is a draft in the builder.
