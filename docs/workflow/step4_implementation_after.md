# Step 4: Implementation (After)

_Open only after completing Step 4 Do._

## Effort estimation

For selected cycles, record a separately labeled retrospective scope assessment and actual verification/omissions, never a replacement projection. Record the maintainer comfortable-fit judgment or mark it pending. Include authorized ledger closeout updates in the final stage commit; verify this before leaving Do. Missing judgment does not authorize invented study acceptance. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

## Objective
Run final Step 4 verification gates and prepare handoff.

## Final Verification Checklist
1. Confirm all planned stages were completed and applicable verification was recorded. For documentation-only work, confirm each stage ran the required document-integrity, evidence, link/path, and authorized-file-scope checks, and that each runtime check marked not applicable includes its reason.
2. Confirm each completed stage has a stage-scoped commit that includes the corresponding Step 4 summary update.
3. Run `git log --oneline` and verify:
   - this cycle’s first Step 4 commit contains approved plans and only the [organization allowance](../../RAILSPIKE.md#planning-artifacts); the feature folder and navigation are complete, and the Step 4 summary appears only afterward
   - this cycle’s commit count, starting with its planning commit, is not lower than `1 + number_of_stages`
4. Confirm the Contract: normal UI/CLI flow, end-to-end outcome, and required recovery—not direct-only behavior. For documentation-only work, confirm the intended document outcome, evidence boundary, and allowed file scope instead.
5. Verify scoped deployment, release, external-system, role, migration, and other dependencies in the applicable environment when they are within the approved scope; otherwise record them as not applicable in the Step 4 summary.
6. Confirm documentation is updated, including the finalized Step 4 implementation summary.
7. Report each applicable check as passed, failed, blocked, pending, or inapplicable, with the reason for any other than passed. Identify reproduced baseline failures. A focused pass is never reported as a full-suite or user-outcome result, and the handoff opens with anything unverified, including a stated known user's recovery condition.

## Next
Restore mode state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode). If enabled, save the full completed Step 4 diagnostic report and include only one short debug line linking to the saved log in the handoff. Report once for Step 4, not per stage; save and commit final additions in a separate log-only handoff commit after the final stage, without amending completed commits.

Notify the user for review/handoff. Cycle completion does not imply merge readiness; related new work can use [Follow-up Cycles Before Merge](../../RAILSPIKE.md#follow-up-cycles-before-merge) with distinct artifacts and fresh approvals. If additional scope emerges, return to the appropriate earlier step instead of improvising within Step 4.
