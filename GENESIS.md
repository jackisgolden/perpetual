# GENESIS.md - initializing the base wiki from your whole history

One-time bootstrap: pull every archive of yourself into `00-inbox/genesis/`,
then run the genesis compile. Raw exports stay OUT of git (they're huge and
full of secrets) - only compiled pages are committed.

## 1. collect the raw material

| source | how to export |
|---|---|
| Claude | claude.ai -> Settings -> Privacy -> Export data (emailed JSON) |
| ChatGPT | Settings -> Data controls -> Export (emailed zip: conversations.json) |
| Gemini | takeout.google.com -> Gemini Apps activity |
| other agents | look for settings -> export / data download; else copy-paste the ones that mattered |
| journals (paper) | photograph pages -> `genesis/journal-scans/` (OCR happens in compile) |
| voice memos | drop audio in `genesis/audio/` (raba/whisper transcribes) |
| notes apps | export to markdown/txt if possible; else any format, compile sorts it |
| git repos | already memory - the compiler reads docs/log.md + READMEs directly |

Drop everything in `00-inbox/genesis/<source>/`. Messy is fine.

## 2. the genesis compile (staged - this is a big batch job)

Run on the LOCAL model (this is exactly what free bulk inference is for;
thousands of conversations through a paid API would cost real money).

- pass 1 - digest: every conversation/journal/note -> a short structured
  summary (topics, decisions, dates, people, open threads). Mechanical,
  parallel, local.
- pass 2 - cluster: summaries grouped by province (forge/ledger/coach/...)
  and by recurring theme across years.
- pass 3 - write: each studio compiles its province's first real pages
  from its clusters: "history of", "current state", "open threads".
- pass 4 - review: Gatekeeper reviews province by province. Genesis rule:
  every claim needs a source pointer back to the digest that produced it.
- pass 5 - the mirror: _meta/genesis-report.md - what the record says
  about you across years: recurring themes, abandoned-then-revived ideas,
  things you keep deciding and re-deciding.

## 3. rules

- raw exports are gitignored; digests and pages are committed
- private-to-others content (other people's messages/names): digest keeps
  the fact you talked, not their words
- anchors/ still outranks everything the history says - you today > you then

Start: `./golden.sh compile` after dropping files, or issue the genesis
edict from the board pointing at this file.
