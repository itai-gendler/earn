---
entities:
- entity: submission
  shows:
  - Link
  - Winner position
  - Reward in USD
- entity: listing
  shows:
  - Title
  - Rewards
  - Winners announced at
- entity: talent
  shows:
  - Name
  - Username
  - Photo
entryPoints:
- earn-web: /earn/listing/:slug/submission
---

# Listing submissions

The results of a listing whose winners are announced: the winners by position and every submission.
