---
availability:
- place: earn-web::public
- place: earn-web::signed-in
references:
- kind: code
  role: implementation
  target: src/pages/earn/listing/[slug]/index.tsx
- kind: code
  role: implementation
  target: src/pages/api/listings/details/[slug].ts
- kind: code
  role: implementation
  target: src/features/listings/components/Submission/SubmissionActionButton.tsx
---

# View a listing

Read a listing's details: what is asked, rewards and podium, deadline, region, eligibility questions, point of contact and discussion.
