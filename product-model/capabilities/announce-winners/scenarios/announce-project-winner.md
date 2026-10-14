---
kind: primary
routes:
  web: Web
steps:
- text: The Team member chooses Announce As Winner on a pending project application and confirms
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
- text: The Product makes it the one winner and publishes the results
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    from: Pending
    to: Won
    facts:
    - Winner position
    - Reward in USD
    - Label
  - entity: listing
    effect: changes
    from: Published
    to: Winners Announced
    facts:
    - Winners announced at
    - Deadline
    - Reward amount
    - USD value
  - entity: credit-entry
    effect: creates
    facts:
    - Kind
    - Change
    - Month
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product posts a winner announcement Comment and emails the applicants
  kind: product
  actor: team-member
  entities:
  - entity: comment
    effect: creates
    facts:
    - Message
    - Pinned
    - Kind
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Announce a project winner

## Trigger

A sponsor picks who does the project.

## Outcome

The chosen applicant is the winner; a quote sets the reward.
