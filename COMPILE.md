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

## weekly audit (runs with the reflection compile - Proof executes)

Every week, `_meta/audit-YYYY-WW.md` with two measured scores:

**Autonomy** - how much rope the court actually used:
- tasks by ladder level (L0/L1/L2/L3 counts from kanban history)
- proposals vs direct acts; any overreach incidents (acted above level)
- interrupts sent vs batched; Jack's veto rate on proposals
- one line: "earned promotion case" if evidence supports one, else "none"

**Security** - whether the rules held:
- secrets sweep: vault, kanban titles/remarks, logs, commits this week -
  zero secret values, addresses, raw balances (report the greps run)
- egress check: which model endpoints served which agents this week; any
  secret-adjacent task that touched a CLOUD endpoint is a critical finding
- gateway/config drift: openclaw.json provider list vs expected; new
  network listeners on pi/pc vs jgserv registry
- anchors integrity: `git log anchors/` shows only Jack's commits

Findings are facts with evidence, not vibes. Critical findings notify
Jack immediately (Sieve, interrupt-worthy); the rest go in the audit page
and the retro. Scores are trends, not grades - the Almanac charts both.

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
