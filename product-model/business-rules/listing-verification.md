---
appliesTo:
- type: entity
  id: listing
- type: capability
  id: publish-listing
- type: capability
  id: submit-sponsor-verification
references:
- kind: code
  role: implementation
  target: src/features/listing-builder/utils/sponsorVerification.ts
---

# Listings from new or unverified sponsors wait for verification

On Superteam Earn, publishing holds a listing for the Earn team to verify when its sponsor is unverified and has no live listing, has a listing more than two weeks past its deadline without winners, or posts a hackathon track without being a Superteam chapter. Verified sponsors and God Mode users publish directly, a listing that was live before is never held again, and other deployments of Earn publish directly.

## Rationale

Verification protects talent from sponsors who would not review or pay.
