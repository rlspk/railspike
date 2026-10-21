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
