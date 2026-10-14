---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
- entity: membership
  verb: holds
  cardinality: one-to-many
- entity: listing
  verb: is point of contact for
  cardinality: one-to-many
- entity: comment
  verb: writes
  cardinality: one-to-many
- entity: invitation
  verb: sends
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/features/auth/utils/getSponsorSession.ts
- kind: code
  role: implementation
  target: src/layouts/Sponsor.tsx
---

# Team member

A person on a sponsor's team who works in the sponsor dashboard: they write and publish listings, review submissions, announce and pay winners. A membership's role decides whether they also manage the team.

## Information kept

- **Current sponsor** — the sponsor whose dashboard the person is working in
