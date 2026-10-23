# Step 4: Implementation (Do)

_Open only after completing Step 4 Before._

## Effort estimation

For selected cycles, preserve the entry projection and append total-cycle revisions when discoveries warrant them, before dependent work where possible. Keep changed-scope approval gates; include snapshot updates with the authorized stage summary commit. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

When [extended estimates](../effort-estimation.md#extended-estimates) are enabled, restore each stage's stable identity, original scope/estimate and revision history before working on it. Append a material revision before dependent work where possible, with UTC date, scope, rater/exposure, point/range, driver/uncertainty and reason (new understanding versus changed scope). It is a revised estimate of the **entire scoped stage**, not its remaining work. Retain the original; changed scope still needs renewed normal approval. Reassess the independent whole-cycle projection when warranted rather than adding stage deltas to it.

At stage completion, record a separately labeled **retrospective stage-work assessment** and actual verification/omissions; it never replaces the original or revised estimates. Reliable measured work may be recorded separately; otherwise it stays unknown. Include these stage records with the corresponding stage-summary commit. No new estimate snapshot is needed merely for resumption, and no separate per-stage diagnostic report is required.

For blocked/skipped/unavailable stages retain status, reason and prior estimates; do not substitute zero or claim completion. When splitting/replacing stages, keep the original identity, scope, estimates and disposition, link new identities and estimate their new scopes without summing them into the old value. Collect missing older records only at the current date, labeled retrospective when applicable, not as fabricated originals. Omit these supplemental requirements when the extension is off.

## Objective
Execute the plan in atomic stages on a dedicated feature branch, documenting progress and verification as you go.

## Execution Rules
- On resumption and before continuing a stage, restore state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode). Record inherited state below the summary’s navigation bar. Phases and stage boundaries do not trigger reports; pending log additions accompany the next authorized stage commit.
- Work stages sequentially, keeping each stage <2 hours
- Favor the simplest viable implementation first; iterate only when necessary
- Before adding new presentation markup or API payloads, confirm whether a canonical component/contract already exists per the Step 2 inventory and reuse/extend instead of duplicating
- Complete the Step 3 Contract—not just a subsystem, direct route, or preparatory asset. For documentation-only scope, complete the approved document outcome without leaving the allowed file scope.
- Require one stage-scoped commit per completed stage; do not batch multiple stages into one commit
- Commit the stage artifact plus the Step 4 summary update for that stage in the same commit before beginning the next stage

Apply [Enhancement Requests](../../RAILSPIKE.md#enhancement-requests) before incorporating new requests. Keep dispositions and pending outcomes in the summary, restore them on resumption, and record implemented refinements with verification and stage-commit references.

## Stage Boundary Protocol (Required)
At every stage boundary (including Stage 1), complete this sequence before starting the next stage:
1. Finish the approved artifact scope for the current stage only.
2. Run applicable verification for that stage and capture commands/results in the Step 4 summary. For documentation-only scope, run `git diff --check`, confirm changed files are within the approved documentation scope, validate local plan-navigation links and referenced local paths, and confirm findings/recommendations are evidence-backed. Record runtime, UI, deployment, migration, and release checks as not applicable unless the approved document makes a claim requiring one.
3. Update the current stage section in `{feature_name}_step4_implementation_summary.md`.
4. Run `git status --short` and confirm only intended files are included.
5. Commit with a stage-scoped message (example: `feat(stage 3): add rerun-safe historical write path`).
6. Run `git log --oneline --max-count 5` and confirm the new stage commit is present.
7. Only then begin the next stage.

## Implementation Summary Artifact
- Location: `docs/plans/{feature_name}/`, beside the approved plans; create only after the initial planning commit.
- Filename: `{feature_name}_step4_implementation_summary.md`
- Begin with the standard Plan navigation bar (template in `RAILSPIKE.md`; omit skipped Step 1)
- Preferred format per stage:
  - One `## Stage N - {title}` header per completed stage
  - Flat bullets for `Changes`, `Verification`, and `Notes`
  - Nested bullets under those fields when listing multiple concrete items
- Contents per stage:
  - Stage number/name
  - Changes shipped
  - Verification performed (including checks recorded as not applicable and why)
  - Notes/risks
- With extended mode enabled: original stage-work value/scope, linked dated revisions (or explicit unchanged status), and a separate retrospective assessment at completion or unavailable reason. Shared reference/rater/date/exposure metadata can be recorded once where applicable; identities and history must remain unambiguous.

_Template_
```markdown
## Stage X - {title}
- Changes:
- Verification:
- Notes:
- Stage work (extended mode only): original ...; revisions/history ...; retrospective ...
```

Prefer this header-plus-bullets structure over prose paragraphs so the implementation summary stays easy to diff against the Step 3 plan and easy to review at stage boundaries.

Omit the optional stage-work field when extended mode is off. For an active stage, the retrospective field remains pending; fill it only as a separately dated assessment when completion evidence exists. Keep the current view concise and link retained history instead of duplicating snapshots.

For selected study cycles, complete the retrospective assessment and authorized ledger closeout update in the final stage before its commit; record unavailable maintainer judgment as pending.

## Next
After all planned stages are implemented and committed, continue with `docs/workflow/step4_implementation_after.md`.
