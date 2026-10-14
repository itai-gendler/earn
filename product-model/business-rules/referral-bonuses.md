---
appliesTo:
- type: entity
  id: credit-entry
- type: capability
  id: create-talent-profile
- type: capability
  id: announce-winners
references:
- kind: code
  role: implementation
  target: src/features/credits/utils/allocateCredits.ts
- kind: code
  role: implementation
  target: src/app/api/user/complete-profile/route.ts
---

# Referrals earn credits for both talents

A talent who joined with a referral code and their referrer each get a bonus credit when the newcomer's first submission is part of an announced listing, and the referrer gets another for every win of the newcomer. A referral code brings in at most ten people.
