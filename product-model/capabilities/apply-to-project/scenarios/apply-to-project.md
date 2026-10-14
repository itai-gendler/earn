---
kind: primary
routes:
  web: Web
steps:
- text: The Talent chooses Apply Now on an open project
  kind: actor
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Deadline
    - Eligibility questions
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Talent answers the eligibility questions and gives their Telegram handle
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product creates the Submission and charges one credit to this month
  kind: product
  actor: talent
  entities:
  - entity: submission
    effect: creates
    to: Pending
    facts:
    - Eligibility answers
    - Telegram
    - Anything else
    - Label
  - entity: credit-entry
    effect: creates
    facts:
    - Kind
    - Change
    - Month
    with: submission
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product asks Earn's AI reviewer to assess the application and emails the Talent a confirmation
  kind: product
  actor: talent
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Apply to a project

## Trigger

A talent wants to be picked for a project.

## Outcome

The talent has a pending application and one credit fewer this month.
