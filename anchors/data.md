# data classes & routing (hand-written anchor - Jack's law)

Every file the Sieve intakes gets classified, then routed. Class decides
where it lives, what may read it, and what the vault learns.

| class | examples | store | model access | vault gets |
|---|---|---|---|---|
| open | notes, ideas, articles | 00-inbox -> provinces | any | everything |
| court | repos, kanban, configs | git repos | any | everything |
| private | finance raw, journals | private repos / ~/sync | local: full. cloud: never | aggregates + pointers |
| radioactive | medical, legal, IDs, credentials | ~/sync/health (encrypted at rest), sops | local: full. cloud: never | existence, date, category, action items. NO values. |

## medical intake (the pattern for all radioactive data)
1. drop zone: ~/sync/health/inbox/ (syncthing'd pi<->pc, restic-backed,
   NEVER a cloud drive, NEVER a git repo)
2. local pipeline: OCR (tesseract) + local model - which may read
   EVERYTHING, values included; locality is the boundary, not the model ->
   ~/sync/health/index.md (dates, providers, doc types, follow-ups)
3. vault (coach province) receives: "2026-07-20 - labs, provider X,
   follow-up due Sept" - existence and actions, never values
4. retrieval: on a LOCAL model channel, ask anything - full access, no
   friction. On a cloud channel, default answer is the pointer; values
   only on my explicit override, after the Sieve names the channel.

## cloud drive
The court maintains it via rclone from pc. L0: inventory + diff reports.
L2: organize, rename, dedupe within the drive. L1 (propose only):
deletions, sharing changes. Standing migration: radioactive/private class
files found in the cloud get flagged and proposed for migration to local
stores - the drive trends toward staging + non-sensitive shares only.
Weekly hygiene report lands in _meta/ with the audit.
