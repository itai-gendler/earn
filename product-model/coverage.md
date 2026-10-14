---
scope: 'The Superteam Earn web app: listings, submissions and applications, the sponsor dashboard, sponsor teams, talent profiles, credits, the Earn wallet and email preferences.'
method: Static inspection of the Next.js pages, API routes, feature modules and the Prisma schema.
covered:
- description: Listing feeds, listing pages, results and search
  paths:
  - src/features/listings/
  - src/pages/earn/listing/
  - src/pages/earn/listings/
  - src/pages/api/listings/
  - src/app/api/listings/
  - src/features/search/
  - src/pages/api/search/
  - src/pages/earn/index.tsx
  - src/pages/earn/all/
  - src/pages/earn/bounties/
  - src/pages/earn/projects/
  - src/pages/earn/category/
  - src/pages/earn/regions/
  - src/pages/earn/skill/
  - src/pages/earn/search/
  - src/pages/earn/bookmarks/
  - src/features/home/
- description: Submission and application API with credit checks
  paths:
  - src/pages/api/submission/
  - src/features/credits/
  - src/app/api/user/credit/
  - src/app/api/spam-dispute/
- description: Listing builder and its draft, publish, update, unpublish, delete and announce routes
  paths:
  - src/features/listing-builder/
  - src/app/api/sponsor-dashboard/listing/
  - src/app/api/sponsor-dashboard/ai-generate/
  - src/app/api/sponsor-dashboard/templates/
  - src/pages/earn/dashboard/new.tsx
  - src/pages/earn/dashboard/listings/
  - src/pages/api/sponsor/verification.ts
- description: Sponsor dashboard listings, submissions review, AI review, scouts and payments
  paths:
  - src/features/sponsor-dashboard/
  - src/pages/api/sponsor-dashboard/submission/
  - src/pages/api/sponsor-dashboard/listings/
  - src/pages/api/sponsor-dashboard/[slug]/
  - src/app/api/sponsor-dashboard/submissions/
  - src/pages/earn/dashboard/index.tsx
  - src/layouts/Sponsor.tsx
- description: Sponsors, sponsor pages and sponsor teams
  paths:
  - src/pages/api/sponsors/
  - src/pages/api/member-invites/
  - src/pages/api/sponsor-dashboard/members/
  - src/pages/earn/new/
  - src/pages/earn/signup.tsx
  - src/pages/earn/s/
  - src/pages/earn/[sponsor]/
  - src/pages/earn/dashboard/team-settings/
  - src/pages/earn/dashboard/sponsor/
  - src/features/sponsor/utils/
- description: Sign-in, sessions and account creation
  paths:
  - src/features/auth/
  - src/pages/api/auth/
  - src/pages/api/user/create.ts
  - src/pages/earn/signin.tsx
- description: Talent profiles, Proof of Work, Pro upgrade and email preferences
  paths:
  - src/features/talent/
  - src/features/social/
  - src/pages/earn/t/
  - src/pages/api/user/
  - src/app/api/user/
  - src/pages/api/pow/
  - src/pages/earn/pro.tsx
  - src/pages/api/email/unsubscribe.ts
- description: Comments on listings
  paths:
  - src/features/comments/
  - src/pages/api/comment/
- description: Earn wallet, withdrawals and KYC for foundation payouts
  paths:
  - src/features/wallet/
  - src/app/api/wallet/
  - src/features/kyc/
  - src/pages/api/sumsub/
- description: Data schema
  paths:
  - prisma/schema.prisma
exclusions:
- description: UI kit, icons, styles, fonts and static assets
  paths:
  - src/components/
  - src/svg/
  - src/styles/
  - src/theme/
  - public/
- description: Social preview image generation
  paths:
  - src/app/api/dynamic-og/
  - src/features/og/
  - src/app/api/og/
- description: Marketing and landing pages
  paths:
  - src/features/stfun/
  - src/pages/index.tsx
  - src/pages/collaborate.tsx
  - src/pages/fast-track.tsx
  - src/pages/member-perks.tsx
  - src/pages/branding/
  - src/pages/earn/sponsor/index.tsx
  - src/features/sponsor/components/
- description: Developer tooling, editor rules and CI
  paths:
  - .cursor/
  - .github/
  - .husky/
  - .vscode/
  - scripts/
- description: Search engine files
  paths:
  - src/app/sitemap.ts
  - src/app/robots.txt/
unmapped:
- description: Grants, grant applications and tranches
  paths:
  - src/features/grants/
  - src/pages/earn/grants/
  - src/pages/earn/listings/grants/
  - src/pages/api/grants/
  - src/app/api/grants/
  - src/pages/api/grant-application/
  - src/app/api/grant-application/
  - src/pages/api/sponsor-dashboard/grants/
  - src/app/api/sponsor-dashboard/grants/
  - src/app/api/sponsor-dashboard/grant-application/
  - src/pages/earn/dashboard/grants/
  - src/pages/api/sponsor-dashboard/application/
- description: Hackathon pages, hackathon dashboard and hackathon subscriptions
  paths:
  - src/features/hackathon/
  - src/pages/earn/hackathon/
  - src/pages/api/hackathon/
  - src/app/api/hackathon/
  - src/pages/earn/dashboard/hackathon/
  - src/pages/api/sponsor-dashboard/active-hackathons.ts
- description: AI agent API and agent claiming
  paths:
  - src/features/agents/
  - src/pages/api/agents/
  - src/pages/earn/agents/
  - src/app/.well-known/
  - src/pages/earn/claim/
- description: Activity feed and likes
  paths:
  - src/features/feed/
  - src/pages/earn/feed/
  - src/pages/api/feed/
  - src/services/likeService.ts
  - src/pages/api/submission/like.ts
  - src/pages/api/pow/like.ts
- description: Leaderboard
  paths:
  - src/features/leaderboard/
  - src/pages/earn/leaderboard/
- description: Superteam chapters, memberships and local talent profiles
  paths:
  - src/features/chapters/
  - src/features/membership/
  - src/pages/api/chapters/
  - src/pages/earn/dashboard/local-profiles/
  - src/pages/api/sponsor-dashboard/local-talent/
- description: Pro perks, surveys, conversion popups and announcements
  paths:
  - src/app/api/pro/
  - src/features/pro/
  - src/features/surveys/
  - src/features/conversion-popups/
  - src/features/announcements/
- description: Support form and sponsor member details
  paths:
  - src/pages/api/email/manual/
  - src/pages/api/sponsors/usersponsor-details.ts
limitations:
- description: Queued emails and AI jobs whose handling runs in separate Superteam services
  paths:
  - src/features/emails/utils/queueEmail.ts
  - src/features/agents/utils/queueAgent.ts
  - src/lib/earncognitoClient.ts
- description: Inbound email delivery webhook
  paths:
  - src/pages/api/email/webhook/
---

# Coverage
