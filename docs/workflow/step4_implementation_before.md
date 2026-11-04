# Step 4: Implementation (Before)

_Open only after the user responds "Approved Step 3."_

## Effort estimation

For selected cycles, restore study state before setup. Only after verification of approved planning history (or its explicit no-commit override) and creation of the summary, record the Step 4 entry projection there (explicitly reaffirm Step 3 if unchanged), before implementation. The summary belongs in the first implementation-stage commit; checkpoint ledger updates follow the approval commit allowance. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

If [extended estimates](../effort-estimation.md#extended-estimates) are enabled, inherit the mode and copy/link approved stage identities, scopes and original stage-work estimates into the summary **only after the planning gate below**, before implementation. Preserve uncertainty, shared metadata and unavailable reasons; copying an estimate is not a newly independent rating. Late activation or an older resumed cycle records current dated estimates with exposure disclosed and earlier originals missing, not reconstructed.

## Objective
Verify the established cycle branch and approved planning history before implementation starts. For documentation-only work, confirm that the approved Step 2/3 artifacts name the allowed documentation file scope.

On entry or resumption, restore state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode). Inherit Step 3 state when creating the summary after the planning gate below.

Read the [shared implementation standards](implementation_standards.md) on entry or resumption. Confirm the approved plan supplies their required outcome, reuse, risk, and verification evidence before dependent implementation.

## Planning Docs Commit Gate (Required)
After `Approved Step 3` and before any implementation changes:
1. Restore cycle identity, actual approval, existing host feature branch/folder, and any explicit no-commit override. Confirm eligible branch reuse or same-cycle transition history when applicable. Establish the product feature branch before product edits in a split repository.
2. Verify the approved Step 3 commit and earlier approved planning content under the [approval commit gate](../../RAILSPIKE.md#approval-commit-gate). Inspect commit contents, not only messages or an attempted commit. Do not create another identical planning commit.
3. If an older cycle lacks commits or organization, follow the shared recovery rule: preserve actual history, organize safely, and commit only currently approved plans and permitted checkpoint records before implementation. Keep unapproved drafts, implementation, the summary and unrelated changes out. Do not invent historical approval commits. Respect recorded explicit no-commit overrides.
4. Check that feature-folder navigation and the plan index resolve for existing artifacts. Never overwrite conflicting files or change approved substance without renewed approval.
5. Only after this gate passes, create the Step 4 summary in the feature folder, restore its study/debug state and begin Stage 1.

## Next
Continue with `docs/workflow/step4_implementation_do.md`.
