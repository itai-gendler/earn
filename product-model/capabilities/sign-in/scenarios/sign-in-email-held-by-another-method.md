---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor signs in with a method that is new for an email address Earn already knows
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public::sign-in
- text: The Product finds an Account with that email created through another sign-in method and refuses
  kind: condition
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

# Sign-in refused for an email held through another method

## Trigger

A person tries a second way of signing in for the same email.

## Outcome

No second Account is created; the person is asked to sign in the way they first did.

## Edge cases

- Signing in without a verified email linked to the sign-in identity is refused.
