# SECURITY.md - the whole model on one page

## the principle
**The boundary is the network, not the model.** A local model may read
everything Jack owns - medical files, ledgers, journals, secrets-adjacent
configs. Maximum autonomy inside the walls. What is forbidden, absolutely,
is sensitive VALUES crossing the network: no cloud LLM prompts, no cloud
storage, no third-party APIs. Egress is the crime; reading is not.

## the three documents that enforce it
- `anchors/autonomy.md` - the L-ladder (L0 read -> L1 propose -> L2
  act+report -> L3 autonomous routines), hard nevers, secrets clause,
  evidence-based promotion. Jack's file; demotion needs no reason.
- `anchors/data.md` - data classes (open / court / private / radioactive),
  storage routing, the radioactive intake pattern, cloud drive custody.
- `COMPILE.md` weekly audit - Proof measures degree of autonomy (ladder
  usage, overreach, veto rate) and degree of security (secrets sweeps with
  greps shown, egress check per model endpoint, config drift, anchors
  integrity). Critical findings interrupt Jack immediately.

## the cloud-channel tripwire
Answers are egress too. On a cloud-model channel the Sieve answers
sensitive queries with pointers by default; values only on explicit
per-request override, after naming the channel. On a local channel:
no friction at all.

## mirrors
jgserv/AGENTS.md carries the same egress rule for infrastructure secrets;
finance/AGENTS.md carries the aggregates-only export boundary. If any two
of these documents disagree, the stricter one wins until Jack rules.
