---
references:
- kind: code
  role: implementation
  target: src/features/credits/utils/allocateCredits.ts
- kind: code
  role: implementation
  target: src/features/credits/utils/creditAggregate.ts
---

# Credit entry

A change to a talent's submission credits, shown in their credit history.

## Information kept

- **Kind** — submission, spam penalty, win bonus, refund, referral bonus or spam dispute
- **Change** — the credits added or taken
- **Month** — the month whose balance it counts toward
- **Dispute decision** — Pending, Approved or Rejected, for a spam dispute
