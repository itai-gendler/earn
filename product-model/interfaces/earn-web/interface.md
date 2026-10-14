---
type: web
actors:
- visitor
- talent
- team-member
- god-mode-user
entryPoints:
- web: /earn
references:
- kind: code
  role: implementation
  target: src/pages/_app.tsx
- kind: code
  role: implementation
  target: src/pages/earn/index.tsx
- kind: code
  role: implementation
  target: src/layouts/Sponsor.tsx
---

# Earn web app

The Superteam Earn website: the public listing pages, sponsor pages and talent profiles; the signed-in talent features; and the sponsor dashboard.
