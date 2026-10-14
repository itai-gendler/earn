---
kind: primary
routes:
  web: Web
steps:
- text: The Talent opens Email Preferences and turns kinds of email on or off
  kind: actor
  actor: talent
  entities:
  - entity: account
    effect: reads
    facts:
    - Email preferences
  contexts:
    web:
      place: earn-web::signed-in::email-preferences
- text: The Product saves the chosen preferences on the Account, lifting an earlier unsubscribe when any kind is on
  kind: product
  actor: talent
  entities:
  - entity: account
    effect: changes
    facts:
    - Email preferences
  contexts:
    web:
      place: earn-web::signed-in::email-preferences
---

# Change email preferences

## Trigger

A person wants more or fewer emails.

## Outcome

Earn emails the person only in the kinds they kept on.
