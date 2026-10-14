---
entities:
- entity: membership
  shows:
  - Role
  collects:
  - Role
- entity: invitation
  collects:
  - Email
  - Role
- entity: account
  shows:
  - Email
entryPoints:
- earn-web: /earn/dashboard/team-settings
---

# Team Settings

The sponsor's team: members, their roles and invitations.
