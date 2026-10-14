---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor filters the listings by type, category, status, region or skill
  kind: actor
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::public::listings
- text: The Product lists the matching public Listing entries, open ones first by default
  kind: product
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
    - Region
    - Deadline
    - Reward amount
    - Reward token
    - Compensation type
    - Status
    - Submission count
  - entity: sponsor
    effect: reads
    facts:
    - Name
    - Logo
    - Verified
  contexts:
    web:
      place: earn-web::public::listings
---

# Browse open listings

## Trigger

A visitor looks for work to do.

## Outcome

The visitor sees the matching public listings with their rewards and deadlines.

## Edge cases

- Status filters are open, in review, completed and all.
- Region and skill pages show only listings of that region or skill.
