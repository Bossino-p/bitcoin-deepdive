# Bitcoin Deep Dive

A single-page Bitcoin deep dive built from a true bitcoiner's perspective. No fluff, no "for dummies" framing, no calling it "crypto".

**Live site:** https://bossino-p.github.io/bitcoin-deepdive/

---

## What it covers

| # | Section | Status |
|---|---------|--------|
| 1 | **Hero** — manifesto + live network stats (price, supply, block height, next halving) | ✅ |
| 2 | **Origin** — 2008 crisis → whitepaper → genesis block → first transaction | ✅ |
| 3 | **Timeline** — key incidents across three eras (2009–2024) | ✅ |
| 4 | **How It Works** — interactive 5-step transaction walkthrough: UTXO model, broadcast, mempool, proof-of-work simulation, confirmations | ✅ |
| 5 | **Tokenomics** — 21M supply schedule, halving table | ✅ |
| 6 | **Technical Deep Dives** — SegWit, Taproot, Lightning (accordion) | ✅ |
| 7 | **Risk Matrix** — quantum, 51% attack, fee cliff, state attacks, protocol bug, AI | ✅ |
| 8 | **What Bitcoin Represents** — the closer | ✅ |

---

## Stack

- Plain HTML + CSS + vanilla JS — no framework, no build step
- Google Fonts: Bebas Neue (display), Newsreader (body serif), IBM Plex Mono (mono)
- Live data: [mempool.space](https://mempool.space) API for block height/halving progress, CoinGecko public API for BTC price and circulating supply
- Orange and black palette with CSS custom properties throughout

## Notable details

- **Interactive mechanics section** — 5-step transaction walkthrough with a live proof-of-work mining simulation (`setInterval` nonce-grinding, fake hash display, block-found reveal) and a confirmation depth animator
- **Newspaper clipping artefact** — hardcoded newsprint hex colours (`#e8e0cc`, `#1a1610`, etc.) with SVG torn-paper edges; intentionally does not invert in dark mode
- **Three IntersectionObservers** for scroll-triggered fade-ins across different sections, each with appropriate thresholds
- **Ruled-paper background** via `repeating-linear-gradient` on `body`, continuous across all sections
- **Alternating spine timeline** — three-column grid (`1fr | 56px | 1fr`) with milestone, dark-event, halving, and neutral card types

## Project structure

```
index.html          — the single page (all sections, all CSS, all JS)
bitcoin-hero.html   — design reference / token system
bitcoin-section2.html — origin section source
bitcoin-section3.html — timeline section source
bitcoin-section4.html — mechanics section source
CLAUDE.md           — project context for Claude Code
```
