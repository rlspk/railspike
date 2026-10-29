# Step 1: Solution Assessment (Optional)

_Read this file only if the feature is complex enough to require Step 1. Pause again after finishing until the user replies with “Approved Step 1.”_

## Debug state
On entry or resumption, restore and record state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode).

## Effort estimation

For a selected effort-study cycle, restore its study state and preserve intake before detailed inspection; capture the Step 1 projected-total snapshot for the recommended scope before handoff. Unselected cycles have no scoring requirement. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

When [extended estimates](../effort-estimation.md#extended-estimates) are enabled, inherit/record that mode and include a complete scoped-cycle estimate for **every option**, with its main complexity driver and material uncertainty. Use a point or range against the frozen references, common starting assumptions and explicit outcome differences. If references are unavailable, give the reason instead of a number; preserve the recommended-cycle snapshot separately. Re-estimate combined/revised options with stable identities and append scope/score changes; do not sum alternatives. No additional option fields are required when the extension is off.

## Objective
Resolve uncertainty when there are multiple viable approaches, complex trade-offs, or an unclear direction before investing in further planning.

## Deliverable
- Ultra-concise comparison document (≤1 page) located in `docs/plans/`
- Filename: `{feature_name}_step1_solution_assessment.md`

## Structure
- Include **Concepts touched**, with candidates by option where needed; follow [concept guidance](../concepts.md#planning).
- Standard Plan navigation bar (template in `RAILSPIKE.md`)
- `## Original Query` first: preserve the request except grammar, spelling, capitalization, punctuation, and formatting fixes; do not summarize or omit anything
- When the query alone would leave the requested outcome unclear, follow it with `## Understood Intent`: a brief, clearly labeled statement of the inferred goal and relevant context. Do not invent scope or replace the original query; omit this section when it adds no useful clarification.
- Problem statement (1 sentence)
- ≥2 solution options tagged sequentially (Option A/B/C/etc.). After its estimate line when enabled, start each option with one concise standalone paragraph explaining the approach and how it addresses the problem, then list pros/cons as bullets.
- Recommendation, including vertical-slice viability
- In extended mode, put a standalone bold `Estimate: <value>` line directly beneath each option heading, before its approach paragraph; keep driver/uncertainty and shared metadata separate. Use a dedicated estimate column for a comparison table. Follow [estimate presentation](../effort-estimation.md#estimate-presentation), including the separate cycle estimate and plain numbers without approximation signs.
- Sign beneath each authored/revised contribution using [agent attribution](../../RAILSPIKE.md#agent-attribution); include model/settings only when verified and preserve prior signatures.

## Guardrails
- Keep content at a high level; no implementation details, code, or verbose prose
- Favor bullets over paragraphs for fast comparisons

Record incidental requests and their disposition under [Enhancement Requests](../../RAILSPIKE.md#enhancement-requests) in this artifact; revisions do not approve advancement.

## Review and revision
Treat the options as material for discussion. The user may choose one, combine compatible parts, reject assumptions, or ask for another approach. Revise the current assessment and recommendation, rechecking compatibility, tradeoffs, risks, and scope. Preserve the Original Query; record the revised direction separately. A request for changes does not approve the step or authorize Step 2.

## Next
Before the completed-step handoff, restore mode state and, if enabled, save the full diagnostic report under [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode) and include only one short debug line linking to the saved log in the handoff, before approval.

Share the document for review and stop. Do not create Step 2 until the user explicitly responds with “Approved Step 1.” When approval arrives, continue with `docs/workflow/step2_feature_description.md`.
