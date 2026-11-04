# Step 3: Development Plan (Before)

_Open only after the user responds "Approved Step 2."_

## Effort estimation

Restore selected-cycle study state and frozen references alongside debug state; recover earlier snapshots without backfilling missing scores. Confirm ledger bookkeeping is inside the approved scope before planning writes. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

Restore inherited [extended-estimate mode](../effort-estimation.md#extended-estimates), using the canonical precedence and legacy-recovery rules; the enabled fallback applies only to new enrolled cycles. If enabled, carry the mode into the plan and prepare stable stage identities; unavailable references leave affected estimates explicitly unavailable rather than fabricated.

## Objective
Confirm the planning boundary and artifact setup before drafting Step 3.

## Before Checklist
- On entry or resumption, restore state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode) and carry it into the Step 3 artifact.
- Confirm Step 2 is approved and no new scope was added after approval.
- Verify the approved Step 2 commit and this cycle's earlier planning history under the [approval commit gate](../../RAILSPIKE.md#approval-commit-gate), or restore its explicit no-commit override. Resolve omissions before drafting.
- Prepare the Step 3 artifact in the existing `docs/plans/{feature_name}/` folder.
- Keep the Step 3 draft and other unapproved revisions uncommitted; retain earlier approved commits.
- Apply the [instruction summary contract](../../RAILSPIKE.md#instruction-summaries) before starting Step 3 drafting.

Before drafting, reconcile recorded requests against approved Step 2 under [Enhancement Requests](../../RAILSPIKE.md#enhancement-requests); changed requirements need renewed approval.

## Next
When all checks pass, continue with `docs/workflow/step3_development_plan_do.md`.
