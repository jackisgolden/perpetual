# perpetual

A wiki about my life that writes itself. The Golden Edict (my 12-agent
court, see [golden-edict](https://github.com/jackisgolden/edict)) reads
what I did, compiles it into these pages nightly, and reads the pages
back as its own memory tomorrow. I open the same folder in Obsidian and
read it. I never maintain it - I only correct it, and my corrections
outrank everything.

## how it works

Three layers, all markdown, all in git:

1. **knowledge** - the pages in this repo. What is known.
2. **process** - the court's SOULs + this repo's COMPILE.md. How pages
   get made and maintained.
3. **governance** - golden-edict/AMENDMENTS.md. How the process itself
   may change. The tower ends at the human.

Every night: new material in `00-inbox/` -> studios compile their
provinces on a dated branch -> the Gatekeeper reviews the diff
(provenance present? anchors untouched? claims traceable?) -> approved
diffs merge. Hallucinations die in review, not in memory.

## layout

    00-inbox/    drop zone - notes, transcripts, exports, session artifacts
    anchors/     hand-written. rules, goals, curriculum. agents READ ONLY.
    rigger/      compiled: infrastructure (jgserv, tailnet, backups)
    forge/       compiled: code, math, music tooling
    ledger/      compiled: money - aggregates and trends ONLY
    atelier/     compiled: writing, drawing, music, aesthetics
    proof/       compiled: tests, audits, what's verified
    coach/       compiled: training, cooking, study progress
    daily/       morning briefs
    _meta/       compile logs, contradictions, open questions, metrics

## the two rules

1. Agent pages carry frontmatter (`compiled: true`, owner, sources, task,
   updated, state). **A page without it is mine. Agents never touch it.**
2. Nothing merges without review (contract: COMPILE.md).

## knowledge ages: the compression heuristic

Understanding compresses (minimum description length: you've learned a
thing when your description of it shrinks without losing predictive
power). The vault enforces this as a lifecycle on every compiled page:

- `state: fresh` - newly learned. Verbose, over-linked, tentative. Fine.
- `state: condensing` - each compile must SHORTEN it. A condensing page
  that grew without new sources is a compile failure.
- `state: hardened` - short, canonical, stable. Left alone until evidence
  contradicts it, which demotes it back to condensing.

The Almanac charts bytes-per-topic over time in `_meta/`. A falling curve
while artifacts keep passing (tests, builds, trades) is proof of
studying. A flat curve is a stall alarm. Yearly git tags are the growth
rings. Perfect compression is uncomputable, so the vault is never done -
it only keeps contracting.

## the anchor pattern

To put anything under management, write one hand-written file in
`anchors/` and let the court do the rest. No new machinery, ever.
Example: `anchors/curriculum.md` is the whole study system - the Coach
compiles progress against it nightly, builds the spaced-review queue,
and Sunrise surfaces what's due. The vault personalizes to whatever the
anchors say the owner cares about.

One habit worth the friction: after a study block, explain what you
learned in one paragraph and drop it in the inbox. Teaching is the
strongest consolidation mechanism there is, and this student keeps notes
forever. Same artifact feeds the spaced-review queue.

## bootstrap and daily use

- full-history bootstrap (chat exports, journals, voice memos): GENESIS.md
- daily driving happens from the golden-edict repo:
  `./golden.sh up | compile | status | down`
- raw financial data never enters this vault. The Ledger studio compiles
  aggregates from the private finance repo; balances, account numbers,
  and addresses stay out. Proof audits for leaks weekly.
