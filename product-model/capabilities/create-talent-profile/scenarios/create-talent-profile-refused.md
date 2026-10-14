---
kind: validation
routes:
  web: Web
steps:
- text: The Talent lists development skills but gives no GitHub
  kind: actor
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::talent-onboarding
- text: The Product refuses the profile and asks for GitHub
  kind: condition
  actor: talent
  entities: []
  contexts:
    web:
      place: earn-web::signed-in::talent-onboarding
---

# Talent profile refused

## Trigger

A developer leaves out their GitHub.

## Outcome

No profile is saved until the missing social is given.

## Edge cases

- Without development skills, an X handle is required instead.
- A username already taken is refused.
- A location in a sanctioned country is refused.
