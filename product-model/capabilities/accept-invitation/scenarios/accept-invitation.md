---
kind: primary
routes:
  web: Web
steps:
- text: The Team member, signed in with the invited email, opens the Invitation link and accepts
  kind: actor
  actor: team-member
  entities:
  - entity: invitation
    effect: reads
    facts:
    - Email
    - Role
  - entity: sponsor
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: earn-web::signed-in::invitation
- text: The Product adds them to the team with the invited role, makes the Sponsor their current sponsor and uses up the Invitation
  kind: product
  actor: team-member
  entities:
  - entity: membership
    effect: creates
    facts:
    - Role
  - entity: team-member
    effect: changes
    facts:
    - Current sponsor
  - entity: invitation
    effect: removes
  - entity: account
    effect: changes
    facts:
    - Email preferences
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::invitation
- text: The Product opens My Listings
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

# Accept an invitation

## Trigger

A person was invited to a sponsor team.

## Outcome

The person is on the team and in the sponsor's dashboard.
