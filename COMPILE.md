# COMPILE.md - the contract agents follow

Read this before touching the vault. The vault is this repo.

1. Work on branch `compile/YYYY-MM-DD`, never on main.
2. Read `00-inbox/` for new material + your province's existing pages.
3. Update ONLY pages in your own province (rigger|forge|ledger|atelier|
   proof|coach, plus daily/ for Sunrise, _meta/ for reflection).
4. Every page you write starts with:
   ---
   compiled: true
   owner: <studio>
   sources: [inbox files or task IDs]
   task: JJC-xxx
   updated: YYYY-MM-DD
   ---
5. NEVER edit: anchors/, or any page lacking `compiled: true`. Those are
   the human's. If a human edited YOUR page (git log shows a non-compile
   commit), treat the human's version as ground truth and compile FROM it.
6. Link generously: [[wikilinks]] across provinces build the graph.
7. Ledger: aggregates and trends only. No account numbers, no raw
   balances, no addresses anywhere in this vault.
8. When done, the Gatekeeper reviews `git diff main...HEAD`:
   frontmatter present? anchors untouched? every claim traceable to a
   source? Approved -> merge to main + delete branch + one-line summary
   in _meta/compile-log.md. Vetoed -> fix and resubmit (max 3 rounds).
9. Processed inbox items move to `00-inbox/archive/`.

## hardness (Jack's design: knowledge has a lifecycle)

Every compiled page carries `state: fresh | condensing | hardened`.

- **fresh** - newly learned. Verbose, heavily linked, tentative. Expected
  to be long and messy; that's what fresh growth looks like.
- **condensing** - under revision. Each compile should SHORTEN it: remove
  scaffolding links, merge duplicates, keep what predicts.
- **hardened** - canonical. Short, stable, rarely edited. Compile passes
  leave it alone unless evidence contradicts it (then it goes back to
  condensing - hardened is not sacred, it's just settled).

Compiler rule: a condensing page that GREW without new source material is
a compile failure - understanding compresses. The Almanac charts
bytes-per-topic over time in `_meta/`; falling curves with passing
artifacts (tests, builds, trades) are the proof of studying. Coach keys
spaced review to state: fresh pages get revisited soon, hardened rarely.
Yearly git tags are the growth rings.
