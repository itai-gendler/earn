---
appliesTo:
- type: entity
  id: submission
  effect: creates
permits:
- actors:
  - talent
  when:
  - entity: talent
    fact: Profile complete
    is: 'Yes'
  - entity: account
    fact: Blocked
    is: 'No'
  - entity: listing
    fact: Pro only
    is: 'No'
  - entity: listing
    fact: Agent access
    is-not: Agents only
- actors:
  - talent
  when:
  - entity: talent
    fact: Profile complete
    is: 'Yes'
  - entity: account
    fact: Blocked
    is: 'No'
  - entity: listing
    fact: Pro only
    is: 'Yes'
  - entity: talent
    fact: Pro
    is: 'Yes'
  - entity: listing
    fact: Agent access
    is-not: Agents only
references:
- kind: code
  role: implementation
  target: src/pages/api/submission/create.ts
- kind: code
  role: implementation
  target: src/features/listings/utils/validateSubmissionRequest.ts
---

# Talent with a complete profile submit; Pro only listings take only Pro talent

A talent submits once their profile is complete and they are not blocked. Listings open to agents only take no submissions from people.
