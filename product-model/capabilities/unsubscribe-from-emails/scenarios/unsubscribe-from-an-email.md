---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor follows the unsubscribe link in an Earn email
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public
- text: The Product marks the address unsubscribed and turns off every email preference of its Account
  kind: product
  actor: visitor
  entities:
  - entity: account
    effect: changes
    facts:
    - Email preferences
  contexts:
    web:
      place: earn-web::public
---

# Unsubscribe from an email

## Trigger

A person no longer wants Earn emails.

## Outcome

Earn sends the address no more emails until the person turns a preference back on.
