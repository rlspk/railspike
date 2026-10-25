# Step 3: Development Plan (After)

_Open only after completing Step 3 Do._

## Effort estimation

For selected cycles, verify the Step 3 snapshot and authorized ledger link, and include the projected total in the handoff. A score does not approve Step 4 or widen the planning-commit allowance. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

If extended mode is enabled, check every stage has its stable identity, a standalone bold estimate line beneath its heading (or explicit unavailable reason), and separate driver/uncertainty. Verify the cycle estimate is visible below the state fields, shared work has an owner, whole-cycle total is independently judged, and original values/scopes remain available for Step 4; do not normalize estimates into stage fractions or infer measured time. Check contribution signatures under [agent attribution](../../RAILSPIKE.md#agent-attribution) regardless of estimate/debug mode, including verified-only model/settings and retained prior authorship.

## Objective
Finalize Step 3 for review, enforce approval gating, and hand off cleanly to Step 4.

## After Checklist
1. Verify <=1 page; Plan navigation, Completion Contract, Key Risks; every stage field; and impact/early-validation/mitigation for risks.
2. Verify stage sizing is still atomic (about <=1 hour per stage) and split oversized stages before review.
3. Verify the plan completes the Contract through normal UI/CLI, including recovery and deployment boundaries. When Step 2 states a known user or environment condition, verify a stage replays each reported failure and that supported-platform evidence alone is not treated as satisfying it. For approved documentation-only work, verify it instead completes the stated document outcome within the allowed file scope and identifies evidence and applicable verification; otherwise rescope in Step 2 or call it internal maintenance.
4. Restore mode state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode). If enabled, save the full completed-step diagnostic report and include only one short debug line linking to the saved log before delivering the approval request. Deliver the Step 3 artifact for review and explicitly request `Approved Step 3`.
5. Stop and wait. Do not begin Step 4 until `Approved Step 3` is received.
6. Keep Step 1-3 planning docs uncommitted here; Step 4 organizes them under the [organization rule](../../RAILSPIKE.md#planning-artifacts) and makes the planning-doc commit first on the feature branch.

## Next
After the user responds `Approved Step 3`, continue with `docs/workflow/step4_implementation_before.md`.
