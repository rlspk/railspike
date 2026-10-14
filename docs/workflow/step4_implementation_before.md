# Step 4: Implementation (Before)

_Open only after the user responds "Approved Step 3."_

## Objective
Set up the Step 4 branch and lock in planning artifacts before implementation starts. For documentation-only work, confirm that the approved Step 2/3 artifacts name the allowed documentation file scope.

On entry or resumption, restore state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode). Inherit Step 3 state when creating the summary after the planning commit.

## Planning Docs Commit Gate (Required)
After `Approved Step 3` and before any implementation changes:
1. Create the Step 4 feature branch, or confirm explicitly requested eligible reuse under [Follow-up Cycles Before Merge](../../RAILSPIKE.md#follow-up-cycles-before-merge). Check distinct cycle identity and artifact destinations before writing.
2. Run `git status --short` and confirm Step 1-3 planning docs are present and unstaged/unchanged as expected.
3. Apply the [organization rule](../../RAILSPIKE.md#planning-artifacts): reuse or create the feature folder, preserve approved content, and repair navigation, references, and the plan index. Stop on conflicts or substantive changes.
4. Make this cycle’s planning commit with approved planning documents and only that rule’s organization allowance; inspect staged contents to exclude implementation, the summary, unrelated plans, and other unapproved auxiliary content. Include this feature’s existing debug log under the organization allowance; moving it must preserve history and mode state.
5. Run `git log --oneline --max-count 1` and confirm that planning-doc commit is at `HEAD`.
6. Only then create the Step 4 summary in the feature folder and begin Stage 1 implementation.

## Next
Continue with `docs/workflow/step4_implementation_do.md`.
