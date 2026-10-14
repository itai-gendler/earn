---
availability:
- place: earn-web::public
- place: earn-web::signed-in
references:
- kind: code
  role: implementation
  target: src/pages/earn/index.tsx
- kind: code
  role: implementation
  target: src/app/api/listings/route.ts
- kind: code
  role: implementation
  target: src/features/listings/utils/query-builder.ts
- kind: code
  role: implementation
  target: src/pages/api/search/[query].ts
- kind: code
  role: implementation
  target: src/pages/earn/bookmarks/index.tsx
---

# Browse listings

Find open bounties and projects on the home, bounties, projects, category, region, skill, search and bookmarks pages, filtered by category, status, region or skill and sorted by date, prize or submissions.
