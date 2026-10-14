---
relations:
- entity: comment
  verb: has reply
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/pages/api/comment/create.ts
---

# Comment

A message in a listing's discussion, or a reply to one.

## Information kept

- **Message** — the text, which may mention people by username
- **Pinned** — whether the point of contact pinned it to the top
- **Kind** — a normal comment, a deadline update or a winner announcement
