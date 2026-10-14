---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Team member opens the Invitation link signed in with the invited email and accepts
  kind: actor
  actor: team-member
  entities:
  - entity: invitation
    effect: reads
    facts:
    - Email
    - Role
  contexts:
    web:
      place: earn-web::signed-in::invitation
  capability: accept-invitation
- text: The Product adds them to the team, makes the Sponsor their current sponsor and uses up the Invitation
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
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::invitation
  capability: accept-invitation
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
  capability: accept-invitation
- text: The Team member looks over the Sponsor's listings
  kind: actor
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
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
  contexts:
    web:
      place: earn-web::signed-in::my-listings
  capability: browse-sponsor-listings
---

# Accept an invitation and open the dashboard

## Trigger

A person was invited to a sponsor team.

## Outcome

The person is on the team and sees the sponsor's listings.
