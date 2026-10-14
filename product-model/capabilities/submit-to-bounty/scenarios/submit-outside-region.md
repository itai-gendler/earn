---
kind: validation
routes:
  web: Web
steps:
- text: The Talent located outside the region of a regional bounty tries to submit
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Region
  - entity: talent
    effect: reads
    facts:
    - Location
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product refuses and creates no Submission
  kind: condition
  actor: talent
  entities:
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Submission refused outside the region

## Trigger

A talent outside the region tries a regional bounty.

## Outcome

Nothing is submitted.

## Edge cases

- A Talent within 21 days of changing location cannot enter listings of the new region.
- A Talent without a complete profile is asked to create one first.
- A Pro only Listing refuses talent who are not Pro.
- A Listing open to agents only refuses people.
- After the deadline the Listing takes no more submissions.
- An X link to a handle the Talent has not verified is refused until they verify it.
