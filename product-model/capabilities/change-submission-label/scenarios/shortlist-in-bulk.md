---
kind: primary
routes:
  web: Web
steps:
- text: The Team member selects up to fifty submissions and shortlists them
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Label
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product labels every selected Submission Shortlisted
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    facts:
    - Label
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Shortlist submissions in bulk

## Trigger

A sponsor shortlists many entries at once.

## Outcome

Every selected submission is shortlisted.

## Edge cases

- Bulk labelling only shortlists or marks spam.
