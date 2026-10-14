---
kind: person
acts: internal
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: src/features/navbar/components/UserMenu.tsx
- kind: code
  role: implementation
  target: src/pages/api/sponsors/list.ts
---

# God Mode user

A member of the Superteam Earn team with God Mode: they create sponsors, work in any sponsor's dashboard and change listings outside the usual limits.
