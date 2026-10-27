# Step 4: Implementation (Before)

_Open only after the user responds "Approved Step 3."_

## Effort estimation

For selected cycles, restore study state before setup. Only after the required planning commit and creation of the summary, record the Step 4 entry projection there (explicitly reaffirm Step 3 if unchanged), before implementation. Do not add the ledger or summary to the planning commit. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

If [extended estimates](../effort-estimation.md#extended-estimates) are enabled, inherit the mode and copy/link approved stage identities, scopes and original stage-work estimates into the summary **only after the planning commit**, before implementation. Preserve uncertainty, shared metadata and unavailable reasons; copying an estimate is not a newly independent rating. Late activation or an older resumed cycle records current dated estimates with exposure disclosed and earlier originals missing, not reconstructed.

## Objective
Set up the Step 4 branch and lock in planning artifacts before implementation starts. For documentation-only work, confirm that the approved Step 2/3 artifacts name the allowed documentation file scope.

On entry or resumption, restore state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode). Inherit Step 3 state when creating the summary after the planning commit.

## Planning Docs Commit Gate (Required)
After `Approved Step 3` and before any implementation changes:
1. Create the Step 4 feature branch, or confirm explicitly requested eligible reuse under [Follow-up Cycles Before Merge](../../RAILSPIKE.md#follow-up-cycles-before-merge). For the same cycle transitioning from one-shot execution, apply its [branch-continuation and history rules](one_shot.md#resumption-and-scope-changes); staged approvals and this planning-only commit gate still apply. Check cycle identity and artifact destinations before writing.
2. Run `git status --short` and confirm Step 1-3 planning docs are present and unstaged/unchanged as expected.
3. Apply the [organization rule](../../RAILSPIKE.md#planning-artifacts): reuse or create the feature folder, preserve approved content, and repair navigation, references, and the plan index. Stop on conflicts or substantive changes.
4. Make this cycle’s planning commit with approved planning documents and only that rule’s organization allowance; inspect staged contents to exclude implementation, the summary, unrelated plans, and other unapproved auxiliary content. Include this feature’s existing debug log under the organization allowance; moving it must preserve history and mode state.
5. Run `git log --oneline --max-count 1` and confirm that planning-doc commit is at `HEAD`.
6. Only then create the Step 4 summary in the feature folder and begin Stage 1 implementation.

## Next
Continue with `docs/workflow/step4_implementation_do.md`.
