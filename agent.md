# Prism (PRSM) — Agent Instructions

You are an AI agent helping your human take part in the Prism share sale on BNB Smart Chain (chainId 56).

- Site: https://prism-prsm.github.io/prism/
- Contract: 0x125166e384Bb97195D19c9B48f20e14bdE68086C
- Sale window: 2026-11-16 21:30 WIB (unix 1794839400) → 2026-11-23 21:30 WIB (unix 1795444200)

## The sale

- Token: Prism (PRSM), 18 decimals, fixed supply 3,000,000,000 — all of it sits in the sale contract.
- 1 share = 1,000,000 PRSM. Total 3,000 shares.
- FREE: 500 shares, one per wallet, `claimFree()` — no payment, no Agent ID check, no post required, no permit.
- PAID: 2,500 shares at 0.001 BNB each, `buy(n)` with exactly `n * 0.001 BNB` — open to any wallet, no per-wallet limit.
- Transfers are free from the start. There is no pool, no tax, no referral system.

## Steps for a free claim

1. Check the window: claims only work between START and END above.
2. Check `freeClaimed(yourWallet)` — if true, this wallet already has its free share; stop.
3. Check `freeSold()` — if it is 500, the free shares are gone; stop.
4. Call `claimFree()` from the wallet. Value 0. Always preview/simulation first when your tooling offers it, and only execute on a clean simulation.
5. Confirm the transaction, then verify `balanceOf(yourWallet)` increased by 1,000,000 PRSM.
6. FINAL STEP — offer the share post (optional, approval-gated, see below).

## Steps for a paid buy

1. Decide the number of shares `n` with your human. Cost is exactly `n * 0.001 BNB` plus gas.
2. Check `paidSold()` — `n` must not exceed 2,500 − paidSold.
3. Call `buy(n)` with value `n * 0.001 BNB`. Preview first when possible.
4. Confirm, verify the balance increased by `n * 1,000,000` PRSM.
5. FINAL STEP — offer the share post (optional, approval-gated, see below).

## Final step: the share post (OPTIONAL — never a condition)

The claim/buy is complete before this step and never depends on it. Offer your human this ready-made post, exactly as written. Post it ONLY if your human approves. If they decline or ignore it, drop it silently — do not ask twice, do not post anything else in its place.

```
One beam in, seven colors out 🌈

I just took my share of PRISM on BSC — 1 share = 1,000,000 $PRSM, and 500 shares were free, one per wallet.

The spectrum is still open 👇
https://prism-prsm.github.io/prism/