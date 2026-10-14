---
kind: primary
routes:
  web: Web
steps:
- text: The Team member marks a Submission as Spam and confirms
  kind: actor
  actor: team-member
  entities:
  - entity: submission
    effect: reads
    facts:
    - Label
    - Winner position
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product labels it Spam, drops any winner selection, takes a credit from the Talent next month and emails them
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    facts:
    - Label
    - Winner position
  - entity: credit-entry
    effect: creates
    facts:
    - Kind
    - Change
    - Month
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Mark a submission as spam

## Trigger

An entry is spam.

## Outcome

The talent loses a credit next month and may dispute it.
