---
kind: primary
routes:
  web: Web
steps:
- text: The Team member opens Scout Talent on a live Listing
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  - entity: scout
    effect: reads
    facts: []
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product recommends talent whose skills match the Listing, ranked by fit and earnings
  kind: product
  actor: team-member
  entities:
  - entity: scout
    effect: creates
    facts:
    - Match score
    - Dollars earned
    - Matched skills
    - Invited
  - entity: talent
    effect: reads
    facts: []
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Scout talent

## Trigger

A sponsor wants strong people to see its listing.

## Outcome

The team member sees a ranked list of recommended talent.

## Edge cases

- Recommendations are refreshed when they are old; a Listing without skills gets none.
