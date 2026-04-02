# λ Forensics — Drift Protocol Exploit · On-Chain Investigation

**Case DRF-2604 · 1 April 2026**

> *"This is not an April Fools joke."* — Drift Protocol, 1 April 2026

---

## Overview

Full forensic post-mortem of the **$285M Drift Protocol exploit** on Solana — the second-largest DeFi hack in Solana history, trailing only Wormhole ($326M, Feb 2022).

This report reconstructs the complete money trail **6 layers deep**, from the Solana vault drain to the Ethereum laundering network, including several findings not present in any public report as of 2 April 2026.

**[→ View the interactive report](https://drift-forensics.vercel.app)**

---

## Key Findings (Unreported)

| # | Finding | Confidence |
|---|---------|-----------|
| 1 | ETH recipient `0xef4326f4` decoded from raw CCTP `deposit_for_burn` instruction data | High |
| 2 | CVT Token Creator (`FnYXwy7qEt`) sent 0.01 SOL to **Drift Multisig #3** on March 23 | High |
| 3 | Laundering wallet `0xbe2f0354` active since **April 2019** — pre-existing DPRK infrastructure | High |
| 4 | Satellite `v2rNWff` had $842K USDC pre-staged **13 seconds before** receiving SOL from HkGz4K | High |
| 5 | **RelayRouterV3** used as secondary bridge layer — potential L2 cluster on Arbitrum/Base | Medium |
| 6 | Upstream funder `B87FQZRibFHK` — deepest untraced node, not identified by any public researcher | Pending |

---

## Attack Summary

| Parameter | Value |
|-----------|-------|
| Date | 1 April 2026 · 16:05 UTC |
| Protocol | Drift Protocol (Solana perp DEX) |
| TVL at time | ~$550M |
| Amount drained | $200M–$285M |
| Time to drain | 12 minutes · 31 withdrawals |
| Preparation | 22 days |
| Attack vector | Durable nonce + social engineering multisig + oracle manipulation |
| CCTP bridged | ~$230M (Circle did not freeze) |
| Attribution | Probable Lazarus Group (DPRK) |

---

## Wallets Tracked

### Solana
| Address | Label | Notes |
|---------|-------|-------|
| `HkGz4KmoZ7Zmk7HN6ndJ31UJ1qZ2qgwQxgVqQwovpZES` | Drift Exploiter 1 | $538K remaining (477K USDY) |
| `FnYXwy7qEtGV4cj1Sf6tht7VDsiytFjJeF9yd4LpAjjx` | CVT Token Creator | Sent SOL to Drift Multisig #3 |
| `v2rNWfftzxposVr5UsuTLHczYbBEATKJVEGoPXmKA28` | Satellite distributor | $926K USDC bridged |

### Ethereum
| Address | Label | Notes |
|---------|-------|-------|
| `0xef4326f42f2eb656c58fabf8b1d3298dc2ab80c6` | CCTP Bridge Hub | Decoded from raw instruction · UNREPORTED |
| `0x63242a4ea82847b20e506b63b0e2e2eff0cc6cb0` | Distribution Hub | $31.9M outflow |
| `0x4f82e73edb06d29ff62c91ec8f5ff06571bdeb29` | Active Launderer | 16.73 ETH · LIVE |
| `0xbe2f0354d970265bfc36d383af77f72736b81b54` | 2019 Infrastructure | Still moving funds |

---

## Methodology

All findings based on: Helius RPC · Etherscan API v2 · CCTP instruction decoding · Solscan · Arkham Intelligence.

No speculation. Every claim is traceable to a specific transaction hash.

---

## About

**λ Forensics** — On-chain forensic intelligence on Solana DeFi.

- X: [@alex_lamport](https://x.com/alex_lamport)

*Generated: 2 April 2026 · Case DRF-2604*
