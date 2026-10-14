---
availability:
- place: earn-web::signed-in
domain: sponsor-profile
references:
- kind: code
  role: implementation
  target: src/pages/api/sponsors/create.ts
- kind: code
  role: implementation
  target: src/pages/earn/new/sponsor.tsx
- kind: code
  role: implementation
  target: src/features/sponsor/utils/sponsorFormSchema.ts
---

# Create a sponsor

Create a sponsor with its name, page address, logo, website, industry, socials, bio, legal entity and location; the creator joins its team as Admin.
