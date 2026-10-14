---
entities:
- entity: talent
  shows:
  - Username
  - Name
  - Photo
  - Bio
  - Location
  - Skills
  - Socials
  - Work details
  - Interests
  - Private profile
  collects:
  - Username
  - Name
  - Photo
  - Bio
  - Location
  - Skills
  - Socials
  - Work details
  - Interests
  - Private profile
- entity: proof-of-work
  shows:
  - Title
  - Description
  - Link
  - Skills
  collects:
  - Title
  - Description
  - Link
  - Skills
entryPoints:
- earn-web: /earn/t/:username/edit
---

# Edit profile

Where a talent changes their profile and their Proof of Work.
