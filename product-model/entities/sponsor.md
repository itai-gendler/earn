---
relations:
- entity: membership
  verb: has
  cardinality: one-to-many
- entity: listing
  verb: posts
  cardinality: one-to-many
- entity: invitation
  verb: issues
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsors/create.ts
- kind: code
  role: implementation
  target: src/pages/api/sponsors/edit.ts
---

# Sponsor

A company, project or Superteam chapter that posts listings on Earn and pays their winners.

## Information kept

- **Name** — the unique sponsor name
- **Slug** — the unique address of the sponsor page
- **Logo** — the sponsor logo
- **Website** — the sponsor website
- **Industry** — the industries the sponsor works in
- **X handle** — the sponsor X handle
- **Bio** — a short description
- **Entity name** — the legal entity behind the sponsor
- **Location** — where the sponsor is based
- **Verified** — whether the Earn team has verified the sponsor
- **Superteam chapter** — whether the sponsor is a local Superteam chapter
- **Verification details** — the Superteam chapter and lead who can vouch for the sponsor, given while a listing is under verification
- **Total rewarded** — the US dollar value the sponsor has rewarded across its listings
