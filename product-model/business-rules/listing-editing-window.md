---
appliesTo:
- type: entity
  id: listing
  effect: changes
  facts:
  - Title
  - Description
  - Skills
  - Region
  - Deadline
  - Winner announcement date
  - Reward token
  - Compensation type
  - Rewards
  - Bonus spots
  - Reward amount
  - Quote range
  - Eligibility questions
  contexts:
  - place: earn-web::signed-in::listing-builder
permits:
- related:
  - verb: posts
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
  when:
  - state: Draft
- related:
  - verb: posts
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
  when:
  - state: Under Verification
- related:
  - verb: posts
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
  when:
  - state: Unpublished
- related:
  - verb: posts
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
  when:
  - state: Published
  - fact: Accepting submissions
    is: 'Yes'
- related:
  - verb: posts
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
  when:
  - state: Published
  - entity: sponsor
    fact: Superteam chapter
    is: 'Yes'
- actors:
  - god-mode-user
references:
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/isListingEditAllowed.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/isListingEditable.ts
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/isListingDraftable.ts
---

# A sponsor edits a listing's details only until its deadline

Drafts, listings under verification and unpublished listings are edited freely. A live listing is edited only while it still accepts submissions; a Superteam chapter may keep editing until winners are announced. God Mode users edit at any time.
