---
entities:
- entity: listing
  shows:
  - Title
  - Type
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
  - Point of contact
  - Pro only
  - Agent access
  - Status
  - Submission count
- entity: sponsor
  shows:
  - Name
  - Logo
  - Verified
- entity: comment
  shows:
  - Message
  - Pinned
  - Kind
entryPoints:
- earn-web: /earn/listing/:slug
---

# Listing

One listing's page: its details, rewards, eligibility and discussion.
