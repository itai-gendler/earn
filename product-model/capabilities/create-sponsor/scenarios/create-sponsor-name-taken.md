---
kind: validation
routes:
  web: Web
steps:
- text: The Team member enters a sponsor name or page address another Sponsor already uses
  kind: actor
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
- text: The Product refuses until both are unique
  kind: condition
  actor: team-member
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
    - Slug
  contexts:
    web:
      place: earn-web::signed-in::sponsor-onboarding
---

# Sponsor name or address taken

## Trigger

A sponsor picks a name already on Earn.

## Outcome

No sponsor is created.
