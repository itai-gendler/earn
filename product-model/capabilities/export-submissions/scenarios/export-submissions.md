---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses to export the submissions of a Listing
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product produces a CSV of every Submission with its Talent and wallet address
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Link
    - Tweet link
    - Anything else
    - Eligibility answers
    - Quote
    - Telegram
    - Label
    - Notes
    - Winner position
  - entity: talent
    effect: reads
    facts:
    - Name
    - Username
    - Photo
    - Location
    - Socials
    - Wallet address
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Export submissions

## Trigger

A sponsor reviews offline or pays outside Earn.

## Outcome

The team member has the spreadsheet.
