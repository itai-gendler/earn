---
appliesTo:
- type: entity
  id: talent
  effect: changes
permits:
- self: true
references:
- kind: code
  role: implementation
  target: src/pages/api/user/edit.ts
- kind: code
  role: implementation
  target: src/app/api/user/complete-profile/route.ts
---

# Talent change only their own profile

Profile details, bookmarks, verified handles, Pro and KYC status all belong to the talent themselves.
