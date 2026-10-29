# Step 2: Feature Description

_Open this only after receiving “Approved Step 1” (or if Step 1 was skipped). Pause again after delivering Step 2 until the user sends “Approved Step 2.”_

## Debug state
On entry or resumption, restore and record state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode).

## Effort estimation

For a selected effort-study cycle, restore study state (and preserve intake if Step 1 was skipped), then capture the Step 2 projected-total snapshot before handoff. Include authorized ledger bookkeeping in the delivery scope. Preserve earlier snapshots on revisions. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

Inherit any recorded [extended-estimate mode](../effort-estimation.md#extended-estimates); it does not require a repeated selection question. Keep the scoped-cycle projection here distinct from stage-work annotations planned in Step 3.

Display the enrolled cycle's estimate on a standalone bold `Cycle estimate: <value>` line below the state fields, following [estimate presentation](../effort-estimation.md#estimate-presentation). Sign beneath authored/revised contributions using [agent attribution](../../RAILSPIKE.md#agent-attribution), with model/settings only when verified. Attribution applies even without estimates.

## Objective
Capture the problem framing, desired outcomes, and shared-component considerations before planning implementation work.

## Deliverable
- Concise doc (≤1 page) stored in `docs/plans/`
- Filename: `{feature_name}_step2_feature_description.md`

## Structure
- Include **Concepts touched** and proposed inventory additions/corrections within delivery scope; follow [concept guidance](../concepts.md#planning).
- Standard Plan navigation bar (template in `RAILSPIKE.md`; omit skipped Step 1)
- Problem: 1–2 sentences
- User stories: bullet list in the format “As [role], I want [goal] so that [benefit]”
- Core requirements: 3–5 bullets capturing non-negotiable behaviors
- Delivery scope:
  - Work type: application change or documentation-only
  - For documentation-only work: allowed documentation files or directories, intended audience/outcome, and an explicit statement that application/runtime changes are not permitted
- Completion boundary: for application work, normal entry, end-to-end outcome, needed recovery, and release condition; for documentation-only work, document completion, intended audience outcome, correction/recovery path, and handoff condition
- Known user or environment: when the request names a user, machine, or environment, state that user's ordinary entry point and recovery condition: the mismatch or failure to handle, the next action they can take unaided, how they verify success or retry, and the evidence that will show it. Evidence from a different supported platform does not satisfy this condition; omit the item when no user or environment is named
- Risks (2–4): impact, earliest validation, mitigation before Step 3
- Shared component inventory: enumerate every existing UI/API surface that already renders the data; specify whether the feature reuses/extends the canonical component or needs a new one (with rationale)
- Simple user flow: numbered steps
- Success criteria: measurable outcomes that confirm the feature solves the problem

Apply [Enhancement Requests](../../RAILSPIKE.md#enhancement-requests) when revising scope; retain pending requests and approval status in this artifact.

## Guardrails
- Avoid implementation details, code, database schema, UI mockups, or verbose descriptions
- Surface material risks; do not bury them in other sections
- A feature is a normal-flow vertical slice, not a component, API, cache, migration, or hidden route; otherwise call it internal maintenance
- Documentation-only scope is valid when the deliverable itself is the outcome. It must name the allowed file scope; do not use it to make application, CI, deployment, or generated-artifact changes without returning to Step 2 for approval.
- Keep the doc lightweight enough to consume at a glance

## Next
Before the completed-step handoff, restore mode state and, if enabled, save the full diagnostic report under [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode) and include only one short debug line linking to the saved log in the handoff, before approval.

Deliver the document, request confirmation, and wait for "Approved Step 2." Once approved, continue with `docs/workflow/step3_development_plan_before.md`.
