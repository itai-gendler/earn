---
entities:
- entity: listing
  shows:
  - Title
  - Type
  - Status
  - Deadline
  - Rewards
  - Bonus spots
  - Reward token
  - Submission count
  - Payments made
- entity: submission
  shows:
  - Link
  - Tweet link
  - Anything else
  - Eligibility answers
  - Quote
  - Telegram
  - Label
  - Notes
  - AI review
  - Winner position
  - Reward in USD
  - Payments
  collects:
  - Label
  - Notes
  - Winner position
  - Payments
- entity: talent
  shows:
  - Name
  - Username
  - Photo
  - Location
  - Socials
  - Wallet address
  - KYC verified
- entity: scout
  shows:
  - Match score
  - Dollars earned
  - Matched skills
  - Invited
entryPoints:
- earn-web: /earn/dashboard/listings/:slug/submissions
---

# Submissions

A listing's submissions in the sponsor dashboard, with its Scout Talent and Payments tabs.
