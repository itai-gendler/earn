---
kind: primary
routes:
  web: Web
steps:
- text: The Team member picks another Sponsor whose team they belong to
  kind: actor
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
  - entity: team-member
    effect: reads
    facts:
    - Current sponsor
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product makes it their current sponsor and shows its listings
  kind: product
  actor: team-member
  entities:
  - entity: team-member
    effect: changes
    facts:
    - Current sponsor
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
    - Status
    - Deadline
    - Reward amount
    - Reward token
    - Submission count
    - Payments made
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# Switch sponsor

## Trigger

A person works for several sponsors.

## Outcome

The dashboard shows the chosen sponsor.

## Edge cases

- A God Mode user may pick any Sponsor.
