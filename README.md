# Bitcoin Deep Dive

A single-page Bitcoin deep dive built from a true bitcoiner's perspective. No fluff, no "for dummies" framing, no calling it "crypto".

**Live site:** https://bossino-p.github.io/bitcoin-deepdive/

---

## What it covers

| # | Section | Status |
|---|---------|--------|
| 01 | **Hero** — manifesto + live network stats (price, supply, block height, next halving) | ✅ |
| 02 | **Origin** — 2008 crisis → whitepaper → genesis block → first transaction | ✅ |
| 03 | **Timeline** — key incidents across three eras (2009–2024) | ✅ |
| 04 | **How It Works** — interactive 5-step transaction walkthrough: UTXO model, broadcast, mempool, proof-of-work simulation, confirmations | ✅ |
| 05 | **Tokenomics** — 21M supply schedule, halving countdown table | ✅ |
| 06 | **Technical Deep Dives** — SegWit, Taproot, Schnorr, Lightning, Ordinals/BRC-20, hashrate, UTXO set, sats/denominations, nodes (accordion) | ✅ |
| 06b | **Self-Custody** — seed phrase storage, $5 wrench attack, multisig 2-of-3 setup, inheritance planning (accordion) | ✅ |
| 08 | **Risk Matrix** — quantum computing, 51% attack, fee cliff, state-level attack, protocol bug, AI threats | ✅ |
| 09 | **Reading List** — curated deep-cut books with hardcoded distinct palettes per title | ✅ |
| 10 | **What It Means** — the closer: live network uptime counter since genesis block | ✅ |

---

## Stack

- Plain HTML + CSS + vanilla JS — no framework, no build step
- Google Fonts: Bebas Neue (display), Newsreader (body serif), IBM Plex Mono (mono)
- Live data: [mempool.space](https://mempool.space) API for block height/halving progress, CoinGecko public API for BTC price and circulating supply
- Orange and black palette with CSS custom properties throughout

## Notable details

- **Interactive mechanics section** — 5-step transaction walkthrough with a live proof-of-work mining simulation (`setInterval` nonce-grinding, fake hash display, block-found reveal) and a confirmation depth animator
- **Live uptime counter** — ticks from genesis block `2009-01-03T18:15:05Z`, updated every second
- **Self-custody accordion** — severity-stripped cards (critical / high / medium) with do/don't checklists, 2-of-3 multisig diagram, and inheritance planning steps
- **Sidenav** — fixed left edge, dots-only when collapsed, expands on hover, fades in when hero scrolls out of view; tracks all 10 sections
- **Newspaper clipping artefact** — hardcoded newsprint hex colours (`#e8e0cc`, `#1a1610`, etc.) with SVG torn-paper edges; intentionally does not invert in dark mode
- **Multiple IntersectionObservers** — one per section, each scoped to its own class, avoiding double-handling with the page-wide fade observer
- **Ruled-paper background** via `repeating-linear-gradient`, continuous across all sections
- **Alternating spine timeline** — three-column grid (`1fr | 56px | 1fr`) with milestone, dark-event, halving, and neutral card types

## Project structure

```
index.html              — the single page (all sections, all CSS, all JS)
bitcoin-hero.html       — design reference / hero section source
bitcoin-section2.html   — origin section source
bitcoin-section3.html   — timeline section source
bitcoin-section4.html   — mechanics section source
bitcoin-section5.html   — tokenomics section source
bitcoin-section6.html   — technical deep dives section source
bitcoin-section6b.html  — self-custody section source
bitcoin-section7.html   — risk matrix section source
bitcoin-section8.html   — reading list section source
bitcoin-section9.html   — what it means section source
bitcoin-sidenav.html    — sidenav component source
CLAUDE.md               — project context for Claude Code
```
