---
id: superteam-earn
summary: Open-source bounty and project marketplace where crypto sponsors post listings, talent submits work or applies, and sponsors pick and pay the winners.
category: freelance-marketplace
tags:
- bounties
- freelance
- crypto
- solana
- talent-marketplace
authors:
- name: Superteam
  url: https://github.com/SuperteamDAO
license: AGPL-3.0-only
languages:
- en
limitations:
- People sign in with Google or with a code emailed to them; Earn keeps no passwords.
- 'Rewards are paid in Solana tokens: sponsors pay winners from their own wallet, and Superteam pays the winners of foundation-paid listings.'
- The Earn team decides listing verification and spam disputes outside Earn.
- Earn queues its emails and channel announcements; separate Superteam services deliver them.
- Each person holds one account per email address.
references:
- kind: code
  role: implementation
  target: README.md
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: CONTRIBUTING.md
---

# Superteam Earn

Superteam Earn is a marketplace for crypto work. Sponsors, crypto companies and Superteam chapters, post listings: bounties, where anyone eligible submits finished work and the sponsor ranks the best entries on a podium, and projects, where talent applies or sends a quote and the sponsor picks one person. Talent build a profile with their skills, browse listings by category, region and skill, submit within a monthly allowance of submission credits, and receive rewards in an Earn wallet they can withdraw from. Sponsors work from a dashboard where their team writes and publishes listings, reviews and labels submissions, selects and announces winners, and pays them on-chain. Comments, mentions and email preferences keep both sides informed.

## Intent

An open source platform connecting crypto founders with elite talent to create bounties and accelerate project completion: sponsors get work done by the community, and talent earn in crypto by contributing to the projects they care about.
