---
appliesTo:
- type: entity
  id: invitation
  effect: creates
permits:
- related:
  - verb: issues
    entity: sponsor
  - verb: has
    entity: membership
  - verb: holds
    entity: team-member
  when:
  - entity: membership
    fact: Role
    is: Admin
- actors:
  - god-mode-user
references:
- kind: code
  role: implementation
  target: src/pages/api/member-invites/send.ts
---

# Admins and God Mode users invite people to the team

Members cannot invite. An invitation lasts seven days and is not sent to blocked addresses.
