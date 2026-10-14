---
relations:
- entity: credit-entry
  verb: is charged in
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/pages/api/submission/create.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsor-dashboard/submission/toggle-winner.ts
---

# Submission

A talent's entry to a listing: finished work for a bounty, or an application, with an optional quote, for a project.

## Information kept

- **Link** — the link to the work; required for bounties
- **Tweet link** — the X post sharing the work
- **Anything else** — free-form notes from the talent
- **Eligibility answers** — the answers to the listing's eligibility questions
- **Quote** — the compensation a project applicant asks for, on projects with range or variable compensation
- **Telegram** — the applicant's Telegram handle, on projects
- **Label** — the sponsor's review label: Unreviewed, Reviewed, Shortlisted, Low, Mid or High quality, Needs review, Inaccessible or Spam
- **Notes** — the sponsor team's private notes
- **AI review** — the label and note Earn's AI reviewer suggests, until a team member applies them
- **Winner position** — the podium place or bonus spot chosen for it
- **Reward in USD** — the US dollar value of its reward, set when winners are announced
- **Payments** — each payment made to the winner: transaction, amount and tranche

## States

### Pending

Submitted and awaiting the sponsor.

### Winner selected

Chosen for a winning position; results not yet announced.

### Won

Announced as a winner and awaiting full payment.

### Paid

The winner has been paid in full.

### Rejected

A project application the sponsor turned down.
