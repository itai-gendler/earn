---
appliesTo:
- type: entity
  id: credit-entry
- type: capability
  id: change-submission-label
- type: capability
  id: announce-winners
- type: capability
  id: unpublish-listing
references:
- kind: code
  role: implementation
  target: src/features/credits/utils/allocateCredits.ts
---

# Spam costs a credit next month; wins and refunds give one back

Marking a submission Spam takes a credit from the talent's next month. Each win gives a bonus credit next month, and unpublishing a listing refunds next month the credit each of its submissions cost.
