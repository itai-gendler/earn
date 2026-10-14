---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
- entity: submission
  verb: submits
  cardinality: one-to-many
- entity: comment
  verb: writes
  cardinality: one-to-many
- entity: proof-of-work
  verb: adds
  cardinality: one-to-many
- entity: credit-entry
  verb: earns
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/app/api/user/complete-profile/route.ts
- kind: code
  role: implementation
  target: src/pages/api/user/edit.ts
- kind: code
  role: implementation
  target: src/features/talent/schema/index.ts
---

# Talent

A person who builds a profile on Earn, submits work to bounties, applies to projects and receives rewards.

## Information kept

- **Username** — the unique handle in the profile address
- **Name** — first and last name
- **Photo** — the profile picture
- **Bio** — a short description
- **Location** — the country the talent lives in; it decides which regional listings they may enter
- **Location changed at** — when the talent last replaced an existing location
- **Skills** — skills and sub-skills in development, design, content and other work
- **Socials** — X, GitHub, LinkedIn, Telegram, Discord and website
- **Work details** — work experience, crypto experience, work preference and current employer
- **Interests** — the industries and communities the talent follows
- **Private profile** — whether the profile is kept out of search engines
- **Profile complete** — whether the talent has finished creating their profile
- **Wallet address** — the Earn wallet that receives rewards, created with the profile
- **Referral code** — the code the talent shares to invite others
- **Referred by** — the talent whose referral code this talent used
- **Verified X handles** — the X handles the talent proved they own
- **Pro** — whether the talent is a Pro member
- **Superteam membership** — whether the talent is a recognised member of a Superteam community
- **Total earned** — the US dollar value of the rewards the talent has won
- **Bookmarked listings** — the listings the talent saved
- **KYC verified** — whether the talent passed identity verification for foundation payouts
- **Credit balance** — the submission credits left this month
