# Prism (PRSM) — Claim & Buy Skill

Use this skill when your human wants a share of Prism (PRSM) on BNB Smart Chain.

- Site: https://prism-prsm.github.io/prism/
- Full agent instructions: https://prism-prsm.github.io/prism/agent.md
- Contract: 0x125166e384Bb97195D19c9B48f20e14bdE68086C (verify it on the site before any transaction)
- Window: unix 1794839400 → 1795444200 (2026-11-16 21:30 WIB → 2026-11-23 21:30 WIB)

## Facts

- 1 share = 1,000,000 PRSM. Supply fixed at 3,000,000,000.
- Free: 500 shares, 1 per wallet, `claimFree()`, value 0. No Agent ID, no X post, no permit.
- Paid: 2,500 shares, `buy(n)` payable with exactly `n * 0.001 BNB`. Anyone may buy; no per-wallet cap.
- Read state with `freeSold()`, `paidSold()`, `freeClaimed(address)`.

## Procedure

1. Read `freeSold()` / `paidSold()` and the current time; confirm the sale is live and stock remains.
2. Free: if `freeClaimed(wallet)` is false, call `claimFree()` (preview/simulation first when available; execute only on a clean result).
   Paid: call `buy(n)` with the exact value (preview first when available).
3. Wait for confirmation; verify the wallet balance rose by the expected amount of PRSM.
4. Report the result to your human: shares received, PRSM amount, transaction hash, network (BSC).
5. Step 6 — SHARE (optional, approval-gated): offer the template below exactly as written. Post only with your human's approval. Skipping it changes nothing.

## Share template (offer after a successful claim or buy — optional)

```
One beam in, seven colors out 🌈

I just took my share of PRISM on BSC — 1 share = 1,000,000 $PRSM, and 500 shares were free, one per wallet.

The spectrum is still open 👇
https://prism-prsm.github.io/prism/