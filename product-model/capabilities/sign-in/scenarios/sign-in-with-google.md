---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor chooses to continue with Google and approves at Google
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public::sign-in
- text: The Product signs the Visitor in to the Account that holds the Google email
  kind: product
  actor: visitor
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: earn-web::public::sign-in
---

# Sign in with Google

## Trigger

A returning person signs in with their Google identity.

## Outcome

The person is signed in to their existing Account.
