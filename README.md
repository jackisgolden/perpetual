# perpetual

A wiki about my life that writes itself. Agents (golden-edict) read what I
did, compile it into these pages nightly, and read the pages back as their
memory tomorrow. I open the same folder in Obsidian and just... read it.
I never maintain it. I only correct it - and my corrections outrank
everything.

## layout

    00-inbox/    drop zone: notes, transcripts, task outputs - anything
    anchors/     MY pages. rules and goals. agents may never edit these.
    rigger/      compiled: infrastructure (jgserv, tailnet, backups)
    forge/       compiled: code + math + music tooling
    ledger/      compiled: money (aggregates only - never raw balances)
    atelier/     compiled: writing, drawing, music, aesthetics
    proof/       compiled: tests, audits, what's verified
    coach/       compiled: training, cooking, study
    daily/       morning briefs
    _meta/       compile reports, contradictions, open questions

## the two rules

1. Every agent-written page starts with frontmatter (`compiled: true`,
   owner, sources, task, updated). **A page without it is mine - hands off.**
2. Nothing merges to main without review (see COMPILE.md). Made-up facts
   die in review, not in my memory.

## cadence

Capture always -> compile nightly -> reflect weekly. Run from the
golden-edict repo: `./golden.sh up`, `./golden.sh compile`, `./golden.sh down`.
