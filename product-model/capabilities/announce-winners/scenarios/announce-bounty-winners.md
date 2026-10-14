---
kind: primary
routes:
  web: Web
steps:
- text: The Team member who has filled every podium place chooses Publish Results and confirms
  kind: actor
  actor: team-member
  entities:
  - entity: listing
    effect: reads
    facts:
    - Rewards
    - Bonus spots
    - Deadline
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product publishes the results, closing the Listing at once if its deadline is still ahead and dropping bonus spots left unfilled
  kind: product
  actor: team-member
  entities:
  - entity: listing
    effect: changes
    from: Published
    to: Winners Announced
    facts:
    - Winners announced at
    - Deadline
    - Rewards
    - Bonus spots
    - Reward amount
    - USD value
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product sets each winning Submission to won with its dollar reward and gives each Talent who won a bonus credit next month
  kind: product
  actor: team-member
  entities:
  - entity: submission
    effect: changes
    from: Winner selected
    to: Won
    facts:
    - Reward in USD
    - Label
  - entity: credit-entry
    effect: creates
    facts:
    - Kind
    - Change
    - Month
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
- text: The Product posts a winner announcement Comment and emails the talent who took part
  kind: product
  actor: team-member
  entities:
  - entity: comment
    effect: creates
    facts:
    - Message
    - Pinned
    - Kind
  - entity: talent
    effect: reads
    facts: []
  contexts:
    web:
      place: earn-web::signed-in::submissions
---

# Announce bounty winners

## Trigger

A sponsor has decided its winners.

## Outcome

The results are public, winners are told and payment can begin.

## Decision points

### Who pays

Does Superteam pay this listing?

- foundation paying → the Product asks Superteam to pay winners who passed KYC and asks the others to submit KYC
- otherwise → the winners wait for the sponsor to pay

## Edge cases

- Referral bonuses are given for the first submissions and wins of referred talent.
