---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Reject on a pending project application and confirms
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Eligibility answers
    - Quote
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product rejects the Submission and emails the Talent
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    from: Pending
    to: Rejected
    facts: []
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Reject an application

## Trigger

A sponsor declines an applicant.

## Outcome

The applicant is told and can no longer edit the application.

## Edge cases

- Up to fifty applications can be rejected at once.
