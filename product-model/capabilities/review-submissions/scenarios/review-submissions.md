---
kind: primary
routes:
  web: Web
steps:
- text: The Team member opens the submissions of a Listing and filters by label
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Status
    - Submission count
  - entity: submission
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Team member opens a Submission
  kind: actor
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
  - entity: talent
    effect: reads
    facts:
    - Name
    - Username
    - Photo
    - Location
    - Socials
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Review submissions

## Trigger

A sponsor reviews entries.

## Outcome

The team member sees each entry with who made it.
