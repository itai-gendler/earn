---
kind: primary
routes:
  web: Web
steps:
- text: The Talent adds an X link from a handle they have not verified and chooses to verify
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Talent signs in to X in the window Earn opens
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::listing
- text: The Product adds the handle to the Talent's verified handles
  kind: product
  actor: talent
  entities:
  - entity: talent
    effect: changes
    facts:
    - Verified X handles
  contexts:
    web:
      place: earn-web::signed-in::listing
---

# Verify an X handle

## Trigger

A talent shares work posted on X.

## Outcome

Links from that handle are accepted in their submissions.
