# Step 3: Development Plan (Do)

_Open only after completing Step 3 Before._

On resumption, restore the current artifact’s state using [Railspike Debug Mode](../../RAILSPIKE.md#railspike-debug-mode). This phase does not trigger a diagnostic report.

## Effort estimation

For selected cycles, capture the Step 3 projected-total snapshot after the plan accounts for required verification and recovery. Keep it in the plan and link from the authorized ledger; retain prior values and approval context on revision. Follow [Experimental Effort Estimation](../../RAILSPIKE.md#experimental-effort-estimation).

With [extended estimates](../effort-estimation.md#extended-estimates) enabled, each stage includes **stage work** as a point or range, a short complexity driver and material uncertainty. Cover that stage's full scope, verification, documentation and ordinary correction; identify the owner of shared work without charging whole-cycle planning to every stage. Preserve stable identities, original scopes and dated estimates for Step 4. The independently judged cycle projection is not the stage sum; stage annotations are not remaining effort, hours, cycle observations or percentage complete.

## Objective
Break the feature into atomic implementation stages, identify dependencies, and define verification expectations before coding starts.

## Deliverable
- Numbered plan (<=1 page) saved in `docs/plans/`
- Filename: `{feature_name}_step3_development_plan.md`

## Structure
Include **Concepts touched** and plan the affected inventory updates and checks using [concept guidance](../concepts.md#planning).

Begin with the standard Plan navigation bar (template in `RAILSPIKE.md`; omit skipped Step 1).

Then add `## Completion Contract`: normal entry, end-to-end outcome, required recovery, deployment/external verification, and release condition. For documentation-only work, instead state the approved allowed documentation file scope, intended audience/outcome, document completion/recovery boundary, evidence boundary, and which runtime/deployment checks are not applicable.

Then add `## Key Risks`: impact, early validation, mitigation. Prefix usability, data, or rollback risks `**High risk:**`.

Render the plan using this preferred format for every stage:

```md
## Stage 1

**Estimate: <value>**

- Goal: ...
- Dependencies: ...
- Expected changes: ...
- Verification approach: ...
- Estimate details (extended mode only): driver: ...; uncertainty: ...
- Risks or open questions:
  - Impact: ...
  - Early warning / validation: ...
  - Mitigation: ...
- Canonical components/API contracts touched: ...
```

For each stage include:
- A `## Stage N` header, one stage per section
- Flat bullet items for Goal, Dependencies, Expected changes, Verification approach, Risks or open questions, and Canonical components/API contracts touched
- Conceptual expected changes only; include database/function signature updates without implementations
- Bullet points under Risks or open questions whenever there is more than one item
- Resolve each material risk before dependent work begins
- Canonical components/API contracts as an explicit bullet, not buried in prose
- Include all wiring, operations, and verification needed for the Completion Contract; split stories into vertical slices, not layers
- For documentation-only work, keep every expected change within the approved documentation file scope and identify the evidence and document-integrity checks for that stage
- Include the standalone estimate line and estimate-details bullet only when extended mode is enabled; otherwise omit them. Use plain numbers without approximation signs and show the enrolled cycle's independent `Cycle estimate: <value>` below its state fields. Follow [estimate presentation](../effort-estimation.md#estimate-presentation) for ranges, unavailable values and history.

When one agent generates the entire Step 3 plan in one pass, use a single attribution footer for the whole plan. Use stage-level attribution only for stages subsequently authored or substantively revised separately. Preserve the original plan footer and prior stage attribution when recording revisions. Follow [agent attribution](../../RAILSPIKE.md#agent-attribution), adding model/settings only when verified. Shared reference/date/rater/exposure metadata may appear once in the artifact.

Place the whole-plan footer after all plan sections, including any study checkpoint:

```md
*— Agent name · YYYY-MM-DD UTC*
```

Additional requirements:
- When Step 2 states a known user or environment recovery condition, include a stage that replays each reported failure as acceptance evidence. A pass only on the installer or another supported platform does not complete it; actionable manual guidance can satisfy it when automatic support is out of scope
- Stages should be about <=1 hour or <=50 lines of change; split anything larger before implementation
- Document database changes conceptually (no SQL)
- Include planned function signatures when relevant, without code
- Prefer bullets over prose paragraphs throughout so reviewers can scan the plan quickly

## Guardrails
- Avoid full code, HTML templates, detailed SQL, or verbose explanations
- Keep `## Key Risks` near the top and repeat stage-specific risks
- If the Completion Contract cannot be met, rescope in Step 2; component-only work is internal maintenance
- Do not use documentation-only scope to change application source, tests, CI, deployment configuration, generated artifacts, or another unapproved file class; return to Step 2 if that becomes necessary
- Keep stage count manageable; if work exceeds about eight stages or a day of effort, split into separate features before moving on

## Next
After drafting the Step 3 plan document, continue with `docs/workflow/step3_development_plan_after.md`.
