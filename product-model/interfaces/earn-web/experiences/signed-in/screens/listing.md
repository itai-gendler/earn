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
  collects:
  - Message
- entity: submission
  shows:
  - Link
  - Tweet link
  - Anything else
  - Eligibility answers
  - Quote
  - Telegram
  - Winner position
  - Payments
  collects:
  - Link
  - Tweet link
  - Anything else
  - Eligibility answers
  - Quote
  - Telegram
- entity: talent
  shows:
  - Credit balance
  - Bookmarked listings
  - Verified X handles
  - KYC verified
  - Pro
  - Location
entryPoints:
- earn-web: /earn/listing/:slug
---

# Listing

One listing's page: its details, rewards, eligibility and discussion, and the talent's own submission.
