---
availability:
- place: earn-web::signed-in
domain: submissions
references:
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/submissions/ai/commit-reviewed/route.ts
- kind: code
  role: implementation
  target: src/app/api/sponsor-dashboard/submissions/ai/unreviewed/route.ts
- kind: code
  role: implementation
  target: src/features/sponsor-dashboard/components/Submissions/Modals/AiReviewBounties.tsx
---

# Run AI Review

Apply the labels and notes Earn's AI reviewer prepared to every unreviewed submission of a listing.
