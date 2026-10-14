---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Invite on a recommended Scout
  kind: actor
  actor: team-member
  entities:
  - entity: scout
    effect: reads
    facts:
    - Match score
    - Invited
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product emails the Talent an invitation to the Listing and marks them invited
  kind: product
  actor: team-member
  entities:
  - entity: scout
    effect: changes
    facts:
    - Invited
  - entity: talent
    effect: reads
    facts: []
  - entity: listing
    effect: reads
    facts:
    - Title
  - entity: invitation
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Invite a scout

## Trigger

A sponsor wants a particular talent to take part.

## Outcome

The talent is invited.
