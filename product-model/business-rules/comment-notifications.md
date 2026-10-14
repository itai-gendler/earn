---
appliesTo:
- type: entity
  id: comment
- type: capability
  id: comment-on-listing
references:
- kind: code
  role: implementation
  target: src/pages/api/comment/create.ts
---

# Comments notify the point of contact, the person replied to and everyone mentioned

A new top-level comment on a listing emails its point of contact unless they wrote it; a reply emails the author of the comment it answers; a mention by username emails the person mentioned. Each email respects the recipient's email preferences.
