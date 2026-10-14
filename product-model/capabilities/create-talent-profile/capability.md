---
availability:
- place: earn-web::signed-in
domain: talent-profile
references:
- kind: code
  role: implementation
  target: src/app/api/user/complete-profile/route.ts
- kind: code
  role: implementation
  target: src/features/talent/components/onboarding-form/Form.tsx
- kind: code
  role: implementation
  target: src/features/talent/schema/index.ts
- kind: code
  role: implementation
  target: src/pages/earn/new/talent.tsx
---

# Create a talent profile

Create the talent profile that lets a signed-in person submit and apply: username, name, photo, location, skills, socials and work details, with an optional referral code.
