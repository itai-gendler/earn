---
appliesTo:
- type: entity
  id: account
  facts:
  - Email preferences
- type: capability
  id: change-email-preferences
- type: capability
  id: unsubscribe-from-emails
references:
- kind: code
  role: implementation
  target: src/pages/api/user/update-email-settings.ts
- kind: code
  role: implementation
  target: src/pages/api/email/unsubscribe.ts
---

# Earn emails a person only in the kinds they keep on

Unsubscribing from any email turns every kind off; turning a kind back on lifts the unsubscribe.
