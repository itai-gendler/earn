---
kind: validation
routes:
  web: Web
steps:
- text: The Team member of a Sponsor with five listings past their deadline and no winners announced chooses Create New Listing
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Status
    - Deadline
  - entity: sponsor
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: earn-web::signed-in::my-listings
- text: The Product refuses until winners are announced on those listings
  kind: condition
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts: []
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::my-listings
---

# New listings blocked by overdue results

## Trigger

A sponsor has left several listings without results.

## Outcome

No new listing is started.
