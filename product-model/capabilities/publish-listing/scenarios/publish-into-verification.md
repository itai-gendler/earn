---
kind: primary
routes:
  web: Web
steps:
- text: The Team member of a new, unverified Sponsor chooses Publish
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product, running as Superteam Earn, finds the Sponsor needs verification
  kind: condition
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Verified
    - Superteam chapter
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
- text: The Product holds the Listing for the Earn team to verify and asks for verification details
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    from: Draft
    to: Under Verification
    facts:
    - Slug
    - Private
    - Pro only
    - Agent access
    - Foundation paying
    - Region
  contexts:
    web:
      place: earn-web::signed-in::listing-builder
---

# Publish into verification

## Trigger

An unverified sponsor publishes its first listing.

## Outcome

The listing waits for the Earn team; it goes live once verified.

## Edge cases

- A Sponsor with a listing more than two weeks past its deadline and no winners announced also waits for verification.
- A hackathon track from a Sponsor that is not a Superteam chapter also waits for verification.
- Other deployments of Earn publish directly.
