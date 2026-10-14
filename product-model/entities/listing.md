---
relations:
- entity: submission
  verb: receives
  cardinality: one-to-many
- entity: comment
  verb: has
  cardinality: one-to-many
- entity: scout
  verb: recommends
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/features/listings/utils/status.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/types/schema.ts
---

# Listing

A bounty, project or hackathon track a sponsor posts. Bounties pay podium places to the best submissions; projects pay one chosen applicant.

## Information kept

- **Title** — the listing name
- **Type** — Bounty, Project or Hackathon track
- **Slug** — the unique address of the listing page
- **Description** — what the sponsor wants done, written in the listing builder
- **Skills** — the skills and sub-skills the work needs
- **Region** — Global, or the country or region whose residents may take part
- **Deadline** — when submissions close
- **Winner announcement date** — the date by which the sponsor commits to announce winners
- **Reward token** — the Solana token the rewards are paid in
- **Compensation type** — fixed, range or variable; bounties are always fixed
- **Rewards** — the amount for each podium place, up to ten places, plus the bonus reward
- **Bonus spots** — how many bonus winners receive the bonus reward
- **Reward amount** — the total reward
- **Quote range** — the lowest and highest quote a project applicant may send, for range compensation
- **Eligibility questions** — the questions every submission answers; each may be optional or ask for a link
- **Point of contact** — the team member who created the listing and the contact handle shown to talent
- **Private** — whether the listing is reachable only through its link
- **Pro only** — whether only Pro talent may submit
- **Agent access** — humans only, agents allowed, or agents only
- **Foundation paying** — whether Superteam pays the winners instead of the sponsor
- **USD value** — the reward in US dollars at the token price when the listing was published
- **Published at** — when the listing first went live
- **Winners announced at** — when the results were published
- **Accepting submissions** — whether the deadline is still ahead and no winners are announced
- **Submission count** — how many submissions the listing has received
- **Payments made** — how many winners have been paid in full
- **Status** — what the dashboard shows: Draft, Under Verification, Unpublished, In Progress before the deadline, In Review after it, Payment Pending once winners are announced, and Completed when every winner is paid

## States

### Draft

Being written in the listing builder and saved as it is edited; only the sponsor team sees it.

### Under Verification

Published by a sponsor the Earn team verifies first; not yet live.

### Published

Live: talent submit until the deadline, then the sponsor reviews.

### Unpublished

Taken down after going live; submissions are closed.

### Winners Announced

Results are public and the winners are being paid.
