# Effort scores and continuing collection

[Workflow](../RAILSPIKE.md#experimental-effort-estimation)

This beta capability estimates relative work for a complete scoped outcome. It does not change approval gates or make small tasks require Railspike. Enable it for a cycle or through a host policy enrolling every future cycle. Keep records in the host project's plans, outside the installed product. No automatic upload occurs.

## Reference R1

**1.0 is the largest well-scoped, releasable slice we would comfortably approve for one Railspike cycle, including required verification and documentation.** Freeform nonnegative decimals estimate total work from the recorded starting point, including inspection, planning, implementation, verification, documentation and ordinary correction. Scores above 1.0 prompt a split discussion. No conversion to hours, line counts, stage fractions or additive forecasts is supported.

These are single-analyst retrospective references, not measured labor. Existing infrastructure is part of each comparison. Record a host-specific reference version if changing their meaning; preserve earlier estimates under their original version.

| Scoped reference | R1 score | Existing capability / qualification |
| --- | ---: | --- |
| Suppress duplicate thread-card preview | 0.10 | Existing shared template; render regression checks |
| Profile-specific about-page copy | 0.20 | Existing profile data and template; preserve other profiles |
| Numeric QDB permalinks | 0.25 | Existing numbering and routing |
| Live QDB score emphasis | 0.30 | Existing voting and renderers; client-state preservation |
| Toolbar identity status | 0.35 | Existing identity storage; server/browser integration |
| Composer decluttering | 0.60 | Existing composer/uploader; required surface verification included |
| Explicit dependency installer | 0.90 | Substantial package/recovery work; historical user-recovery gap prevents a clean anchor |
| Ordinary startup dependency recovery | 1.00 | Existing installer and acceptance machinery; provisional full-cycle reference |
| Private-message history synchronization | 1.20 | Existing signing; coupled protocol/storage/privacy/recovery; discuss split |
| Protected images and portable backup/restore | 1.20 | Existing signing/publication; protected delivery and independent restore; discuss split |

Calibration source identity (2026-10-18, Railspike development study): report SHA-256 `d3a30b6400b83bb25283b4234b41ba07515df9a696ea44de59c10186103771b0`; implementation diff review SHA-256 `068b3519326e08a939df40b5abe0106ddcbab80bd796616c76b5084a21462b84`. These bundled definitions/examples let a new host begin without another local checkout. An existing host's frozen-source rules still apply; restore its sources by hash/revision or explicitly version a replacement. The study's later composer score is 0.60; the original 1.10 remains historical.

## Host ledger

Reuse an existing study ledger. Otherwise create `docs/plans/effort_estimation_study.md` in the host and record study ID `railspike-effort`, reference R1, enrollment policy and its effective UTC date. A host may explicitly enroll all future cycles once; that selects subsequent cycles without repeated questions. Collection remains independent of debug mode.

Use a stable project/cycle ID, for example `project-name/feature-prefix`, and retain any legacy candidate ID as an alias. Same-cycle worktree copies share the ID. Distinct follow-ups have distinct IDs and parent links. Index each cycle with status, scope version, current score/reference, canonical artifact links and acceptance status. Do not restart numbering in each worktree. Integrate ledger updates through ordinary Git review, merging by cycle/checkpoint and preserving disagreements.

Record every enrolled cycle at its first artifact, including those that pause, fail, are superseded or are abandoned. Keep proposed backlog candidates separate from started cycles. Never select only completed successes. When adopting collection for an existing cycle, begin at the current checkpoint, disclose prior exposure and mark earlier checkpoints missing. A skipped optional step is inapplicable, not zero. Zero means no implementation work assigned; retain the row's status to explain why.

## Extended estimates

This optional extension adds detail to a selected effort-study cycle; ordinary study enrollment and whole-cycle checkpoints continue unchanged. Enable it explicitly for a cycle or through a standing host policy for future selected cycles. An extension request does not silently enroll an unselected cycle; establish its study/reference under the normal study setup first. No extra mode question is needed when neither a request nor a policy enables the extension.

Record `Extended estimates: enabled` below the study field in the first applicable artifact, and inherit it through Steps 1–4. Restore explicit mode changes first, then current artifact state, then applicable host policy; an absent field is not opt-out when policy selects the extension. Preserve an existing cycle's recorded disabled state. If selected evidence conflicts and cannot be resolved, clarify before dependent estimation while continuing independent authorized work. An explicit disable is recorded in the current artifact; retain earlier snapshots. Debug state is independent.

- **Option estimate:** total work for that alternative's complete scoped cycle from a stated starting point, including planning, inspection, implementation, verification, documentation and ordinary correction. State outcome differences and assumptions so alternatives are comparable. Keep the recommended-cycle checkpoint separate; a combined option needs a fresh estimate.
- **Stage work estimate:** a supplemental judgment about the entire named stage's scoped work, including its verification, documentation and ordinary correction, using R1 as a reference yardstick. It is not a formal whole-cycle R1 projection, remaining work, a stage fraction or measured time. Include a short driver and material uncertainty as a range or explanation; ranges are subjective, not calibrated intervals. Keep the original stage scope/starting point when revising the total for it.
- **Whole-cycle projection:** continue to judge it independently. Do not sum stages or options, derive time or percentage complete, or count a stage as an independent study outcome. State which stage owns shared verification/documentation; do not charge the cycle's inspection/planning repeatedly to each stage. A supplemental stage value above 1.0 warrants reviewing stage/cycle fit, not conversion into cycle counts.

Use stable option/stage identities with scope version, reference, UTC date, rater/exposure and reason for revision; shared metadata may be stated once per artifact. Show concise current values and link append-only history. The frozen R1 documents and prior cycle-score semantics stay unchanged; stage-level calibration is not established. Missing references use the recovery procedure below and leave affected estimates unavailable, not zero. Resumed older work records estimates from now, without invented originals.

For example, an illustrative two-stage plan might show stage work 0.10 for a shared component and its checks, then 0.20 for integration and its own checks. Shared validation belongs only to its named owner. An independently judged cycle total of 0.45 also includes inspection/planning; neither the stage sum nor subtraction defines it. Illustrative stage history could retain original 0.20, append a whole-stage revision 0.30 after a discovery, and later add retrospective scope 0.25. All remain different records; no actual hours are inferred.

## Recovering frozen references

A frozen source is the exact document version used to define a study's reference scale. Its expected hash comes from the existing ledger or accepted manifest; a hash computed from today's changed document cannot replace that identity. New hosts may start from the bundled R1 examples. Existing hosts retain their recorded source requirements.

1. Read the active study/reference and required source identities. Resolve relative links from the ledger's directory, not the shell directory or installed Railspike. Distinguish a broken path from missing content or a hash mismatch. Inspect the ledger's current recovery notice before treating historical “unavailable” entries as the present state.
2. Verify any retained host-local copy first. Otherwise inspect recorded revisions in accessible local history or an authorized source checkout. Read historical content without switching/resetting a branch or replacing current documents. Retrieve only the required document bytes, not a working-tree or history migration. Another clone is a retrieval source, not an independent observation.
3. Check every required SHA-256 against its recorded expected value **before rating**. Retain verified bytes under a host-owned reference-version directory, outside the installed product. Keep conflicting destination content intact. Plain `.txt` snapshots can preserve Markdown bytes without requiring their historical relative links to work; do not reformat or normalize line endings.
4. Keep a portable provenance manifest beside the snapshots: study/reference version, source label, original repository, exact revision/path when known, expected SHA-256, local cached path relative to the manifest, recovery UTC date and retrieval method. Record unknown provenance as unknown; a matching byte hash does not establish authorship or acceptance. Keep snapshots and manifest together for offline/relocated use; verify against the ledger's identities on reuse.
5. Repair the ledger's source links to the verified local copies, retaining old locations as provenance. Append a dated recovery event without changing historical scores, scopes or missing checkpoints. Record new ratings at their actual current checkpoint; separately label any retrospective reconstruction and its exposure. Preserve unrelated edits when updating shared ledgers.

If a source is still missing, changed or conflicting, identify it and the next recovery action; leave affected numeric ratings unavailable. Do not regenerate frozen text from memory, guess a matching reference, or silently replace it with the bundled examples. An accepted replacement needs an explicit new reference version with earlier sources and scores retained. Source recovery alone never approves implementation, uploads, release publication or study outcomes.

## Snapshot and outcome template

Keep snapshots in the existing feature artifacts; the ledger links to them. Use one dated snapshot per applicable handoff or material revision, explicitly reaffirming unchanged estimates. Resumption alone does not need a duplicate.

```text
Study / stable cycle ID / legacy alias / parent or replacement:
Checkpoint / UTC recorded at / rater and verified model identity if known:
Scope version / starting revision / reference version / protocol version:
Outcome, normal entry, recovery and required evidence / dependencies:
Prior exposure (including source inspection and inherited scores):
Total projected score / reason (scope change, new understanding, or reaffirmation):
Approval context / artifact or immutable revision:
```

Capture intake before detailed inspection where possible, each used Step 1–3 handoff, Step 4 entry after the planning commit, discoveries and closeout. Keep initial scores immutable and append revisions. A second rating is independent only when actually collected before exposure/discussion; do not invent a rater or infer model identity from commit attribution.

At closeout append delivered scope, start/final revisions and stage commits/diffs, planned/completed stages, verification passed/failed/blocked/pending/inapplicable, omitted checks, corrective work versus new requests, and linked splits/follow-ups. Record a **retrospective scope assessment** separately from projections and from the **maintainer comfortable-fit judgment and acceptance date**. Missing judgment stays pending; technical completion is not accepted study completion. Unknown active work stays unknown; calendar time and Git timestamps are not labor measurements.

Keep replaced scope and all child links; never compare reduced scope as completion of the original or count related children/copies as independent trials. Six accepted outcomes can trigger review, but collection continues. Version reference changes and retain old records so future comparisons remain interpretable.
