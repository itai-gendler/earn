---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens a Listing
  kind: actor
  actor: visitor
  entities:
  - entity: listing
    effect: reads
    facts:
    - Title
    - Type
    - Description
    - Skills
    - Region
    - Deadline
    - Winner announcement date
    - Reward token
    - Compensation type
    - Rewards
    - Bonus spots
    - Reward amount
    - Quote range
    - Eligibility questions
    - Point of contact
    - Pro only
    - Agent access
    - Status
    - Submission count
  contexts:
    web:
      place: earn-web::public::listing
- text: The Product shows the Listing with its Sponsor and its Comment thread, pinned ones first
  kind: product
  actor: visitor
  entities:
  - entity: sponsor
    effect: reads
    facts:
    - Name
    - Logo
    - Verified
  - entity: comment
    effect: reads
    facts:
    - Message
    - Pinned
    - Kind
  - entity: listing
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::public::listing
---

# View listing details

## Trigger

A visitor considers taking part.

## Outcome

The visitor knows what is asked, what it pays, who may take part and by when.

## Edge cases

- A regional Listing says which residents may take part.
- A Pro only Listing says only Pro members may submit.
