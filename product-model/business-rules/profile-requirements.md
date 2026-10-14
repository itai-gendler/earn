---
appliesTo:
- type: entity
  id: talent
  facts:
  - Username
  - Socials
  - Location
- type: capability
  id: create-talent-profile
- type: capability
  id: edit-talent-profile
references:
- kind: code
  role: implementation
  target: src/features/talent/schema/index.ts
---

# A talent profile names a unique username and the right social

Talent with development skills give their GitHub; everyone else gives their X handle. Usernames are unique, and a location in a sanctioned country is refused.
