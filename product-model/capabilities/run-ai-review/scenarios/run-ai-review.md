---
kind: primary
routes:
  web: Web
steps:
- text: The Team member starts AI Review on a Listing
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Submission count
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product applies the suggested label and note to every unreviewed pending Submission, shortlisting high-quality project applications
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    facts:
    - Label
    - Notes
    - AI review
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product shows how many were shortlisted, rated mid or low quality, inaccessible or needing review
  kind: product
  actor: team-member
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Run AI Review

## Trigger

A sponsor has many entries to triage.

## Outcome

Unreviewed submissions carry the AI labels and notes for the team to check.
