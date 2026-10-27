# Railspike Failure Modes and Recovery

Railspike is intentionally strict at the points where AI-assisted work most often becomes hard to review. Treat these as stop conditions, not workarounds. Step/phase and stage-commit cases below describe staged execution; one-shot cases use the explicitly selected mode and recorded authorization.

## Approval was skipped

**Signal:** The agent starts a later step or changes implementation before the user explicitly says `Approved Step N`.

**Recovery:** Stop. Review or revise the current artifact; do not keep later work as implicitly approved. Resume only from the last explicitly approved step. If implementation began before `Approved Step 3`, discard or set aside the unapproved implementation and return to planning.

## One-shot authority or instructions are missing

**Signal:** Required project instructions were not read, an agent treats a plan reference or implementation question as execution approval, or a resumed record lacks recoverable authority.

**Recovery:** Read applicable `AGENTS.md` and workflow instructions; resolve missing/unreadable required files before dependent work. Recover the actual user authorization and bounded scope from the record. Answer questions without granting new authority. If permission is missing or ambiguous, ask for the specific execution boundary; do not begin implementation while waiting. Preserve unrelated work and set aside unapproved changes for review without deleting them unilaterally. A question during authorized execution does not by itself cancel that authority. See [one-shot entry and recovery](workflow/one_shot.md).

## A one-shot grows or cannot finish

**Signal:** New scope exceeds recorded authorization, state cannot be recovered, or verification is unavailable.

**Recovery:** Preserve the original record and current changes. Stop dependent work, record the limitation and next permitted action, then obtain renewed bounded authorization or enter staged planning at the earliest affected step. Link records without creating a second study outcome for the same cycle. For missing checks, distinguish technical completion from unverified requirements; do not report a full pass. Retain paused, failed and abandoned outcomes. Follow [transition rules](workflow/one_shot.md#resumption-and-scope-changes).

## Scope expands during Step 4

**Signal:** A newly discovered requirement, new user flow, additional integration, schema change, or material risk is needed to finish a stage.

**Recovery:** Do not fold it into the stage. Record the discovery in the Step 4 summary, finish only the still-valid approved scope if safe, and return to Step 2 (then Step 3) for the expanded work. A new branch or follow-up feature is often clearer.

## The work is documentation-only

**Signal:** The intended outcome is a document, not runtime behavior.

**Recovery:** In a one-shot, record the documentation-only outcome and allowed paths before execution, then apply its document verification requirements. In a staged cycle, Step 2 must call it documentation-only, name the allowed documentation paths, intended audience/outcome, and prohibit application/runtime changes. Step 3 carries that boundary into its Completion Contract. Step 4 verifies document integrity, evidence, local links/paths, and changed-file scope; runtime, UI, deployment, migration, and release checks are marked not applicable with a reason.

## Verification or a stage commit is missing

**Signal:** A planned stage is implemented but its verification is not recorded, its Step 4 summary is not updated, or the work is mixed into a later commit.

**Recovery:** Do not begin the next stage. Run the applicable check, update the current stage section, inspect `git status --short`, and create the missing stage-scoped commit. If later work is already mixed in, separate it into reviewable commits before continuing; record any limitation honestly.

## Passing tests did not establish the user's recovery

**Signal:** A request named a known user or environment, but the handoff reports tests on a different supported platform, or a user still cannot recover.

**Recovery:** Do not treat the pass as completion. In a one-shot, recover the named environment and expected recovery from the record, document missing evidence and verify the actual outcome or seek renewed scope authorization. In a staged cycle, return to Step 2 and state that user's ordinary entry point and recovery condition. Replay each reported failure as acceptance evidence in Step 3, and report the result in Step 4 as passed, failed, blocked, pending, or inapplicable. Manual guidance can be the accepted outcome when automatic support is out of scope.

## A risk blocks a dependent stage

**Signal:** A Step 2 or Step 3 risk has no accepted mitigation or its early validation fails.

**Recovery:** Mark the dependent stage blocked. Resolve, reduce, or re-plan the risk before advancing. Do not make a speculative implementation change simply to keep the sequence moving.

## Minimal pre-handoff check

```bash
git diff --check
git status --short
git log --oneline
```

For one-shot work, confirm actual authority, scope history, verification/omissions, next action, and distinct technical/commit/publication status in the record. Respect no-commit requests; a missing separate planning commit is expected.

For staged work, confirm that the first Step 4 commit contains approved plans and only the [organization allowance](../RAILSPIKE.md#planning-artifacts), every completed stage has a summary update and commit, and the final artifact satisfies the Step 3 Completion Contract.

## Plan organization is blocked

**Signal:** Moving approved plans would overwrite an artifact, leave ambiguous destinations or broken references, or require substantive changes.

**Recovery:** Stop before the planning commit or implementation. Inspect the existing feature folder, preserve filenames and approved content, and resolve collisions without overwriting files. Repair relative links, affected references, and this feature’s plan-index entry. Request renewed approval for substantive revisions. Inspect staged contents against the organization allowance; create the Step 4 summary only after the planning commit.

## Debug state or logging is unclear

**Signal:** Resumed work lacks a reliable mode setting, prior artifacts disagree, a needed project-marker lookup cannot establish the consuming root or file presence, a diagnostic log cannot be saved, a report repeats earlier findings, or routine chat echoes diagnostics instead of linking to the log.

**Recovery:** Apply the [debug contract](../RAILSPIKE.md#railspike-debug-mode): prefer the latest explicit request and current artifact state; historical snapshots do not override them. If evidence cannot resolve resumed state, ask briefly rather than silently defaulting off. Mode changes do not grant approval to proceed.

For a new workflow without an explicit mode request, check for `.railspike_debug_on` only at the established consuming-project root (the host root for vendored/submodule installs). Presence enables the default; absence leaves it disabled. Ignore contents, even “false” or unreadable content when presence is confirmed. Ask if the root or file presence is uncertain, or the path is a directory; do not assume absence or search ancestors. Creating/removing the marker affects future workflows only. Do not use it to resolve uncertain resumed state, and do not alter it for a workflow-specific override.

If saving fails, briefly report the failure without claiming the log was saved or dumping unsaved diagnostics into chat; resolve it before presenting diagnostics as logged. Preserve existing entries and append labeled corrections identifying the superseded entry; skip unchanged reports and link to the existing log without claiming a new entry. Keep full findings and required groups in the log, with inapplicable or uncertain findings separate from redundant instructions. Restore routine enabled handoffs to one short debug link line, without findings or collection narration; present findings in chat only when explicitly requested. Disabled mode preserves the log without new diagnostics or debug links. Preserve ordinary task updates, blockers, approvals, and the [instruction summary contract](../RAILSPIKE.md#instruction-summaries), including explicit requests to show instructions.

For one-shot log timing and commit exceptions, use the [one-shot debug contract](workflow/one_shot.md#study-and-debug-state). In staged cycles, include saved additions only in the authorized planning/stage commit or final log-only handoff commit; never amend completed commits or use the allowance for unrelated files.
