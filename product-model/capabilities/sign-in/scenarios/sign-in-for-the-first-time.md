---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor chooses to continue with email and enters their address
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public::sign-in
- text: The Product emails a one-time code
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public::sign-in
- text: The Visitor enters the code
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: earn-web::public::sign-in
- text: The Product creates an Account for the new address and signs the Visitor in
  kind: product
  actor: visitor
  entities:
  - entity: account
    effect: creates
    facts:
    - Email
    - Blocked
  contexts:
    web:
      place: earn-web::public::sign-in
---

# Sign in for the first time

## Trigger

A visitor who has never used Earn wants to take part.

## Outcome

The person has an Account and is signed in; Earn offers to create a talent profile or a sponsor.

## Edge cases

- Signing in from a page returns the person to that page.
