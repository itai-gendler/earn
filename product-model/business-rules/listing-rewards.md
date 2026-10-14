---
appliesTo:
- type: entity
  id: listing
- type: capability
  id: create-listing
- type: capability
  id: edit-listing
- type: capability
  id: publish-listing
references:
- kind: code
  role: implementation
  target: src/features/listing-builder/types/schema.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/constants/index.ts
---

# A bounty's podium adds up to its reward

A bounty has up to ten podium places numbered from first without gaps, plus an optional bonus reward shared by up to 500 bonus spots; the podium and bonus amounts add up to the reward amount. A project pays a fixed amount, a quote within a range, or a variable quote. Amounts carry at most four decimals.
