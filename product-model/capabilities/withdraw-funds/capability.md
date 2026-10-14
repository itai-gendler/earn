---
availability:
- place: earn-web::signed-in
domain: wallet
references:
- kind: code
  role: implementation
  target: src/app/api/wallet/create-signed-transaction/route.ts
- kind: code
  role: implementation
  target: src/features/wallet/components/withdraw/WithdrawFundsFlow.tsx
- kind: code
  role: implementation
  target: src/features/wallet/utils/withdrawFormSchema.ts
---

# Withdraw funds

Send tokens from the Earn wallet to any Solana address; Earn pays the network fee.
