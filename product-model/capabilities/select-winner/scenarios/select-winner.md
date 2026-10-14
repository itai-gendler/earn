---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Select Winner on a bounty Submission and picks a free place
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Rewards
    - Bonus spots
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product records the place, clearing a Spam label if the Submission had one
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    from: Pending
    to: Winner selected
    facts:
    - Winner position
    - Label
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Select a winner

## Trigger

A sponsor decides a podium.

## Outcome

The submission holds the place until the results are announced.
