# Separate Development Content — Debug Log

## 2026-10-13T07:44:22Z — Step 1

### Necessary/useful instructions
- `RAILSPIKE.md`, Railspike Debug Mode / Durable state and recovery: the explicit user request resolved this new workflow to enabled, recorded immediately below the plan navigation. Retain precedence over project defaults; no marker lookup or modification was needed.
- `docs/workflow/step1_solution_assessment.md`, Structure: comparing alternatives exposed that a minimal copied distribution would not reduce ordinary clone or submodule contents. Retain the comparison and recommendation requirements.
- `RAILSPIKE.md`, Repository Boundary, and Step 1's Understood Intent guidance: distinguished Railspike's upstream records from consuming-project plans and explicitly labeled the interpretation of “cloned into.” Retain both to prevent a cleanup from excluding the host's own planning workflow.
- `docs/workflow/step1_solution_assessment.md`, Guardrails and Next: kept this deliverable at the architectural decision level and stopped at Step 1. Retain the scope and approval boundary; no repository migration is authorized by this assessment.

### Redundant/unnecessary instructions
- `RAILSPIKE.md`, How to Use This Chain item 2 and Key Rules / AI coding agent: both require reprinting the current instructions. This step produced a conversational reprint nearly as long as its assessment, in addition to reading the source. Consolidate the duplicate rule and consider a linked acknowledgment for unchanged instructions; the current requirement was followed.

### Inapplicable instructions
- `RAILSPIKE.md`, Planning Artifacts / Directory structure and organization rule and Commit discipline: feature-folder organization, index updates, branching, and commits apply after Step 3 approval. This new Step 1 and its log remain uncommitted directly under `docs/plans/`; retain the timing restriction.

### Uncertain assessments
- `docs/workflow/step1_solution_assessment.md`, Recommendation, including vertical-slice viability: a lean product plus companion development repository is an end-to-end outcome, but its one-day feasibility depends on the destination and ownership decisions not yet made. Retain the size limit and reassess scope in Steps 2–3 rather than treating this estimate as verified.
- `README.md`, Installation checks / Copy and identify and Verify before welcome: the existing complete-snapshot contract explains the clutter, but no filtered distribution was executed in this step. Any approved separation must update installation and update guidance together; current evidence does not establish that those safeguards are redundant.

## 2026-10-13T07:47:55Z — Step 2

### Necessary/useful instructions
- `docs/workflow/step2_feature_description.md`, Delivery scope and Guardrails: relocation includes scripts and website hosting, so the description explicitly uses the application-change category for distribution/repository maintenance rather than claiming documentation-only authorization. Retain the boundary; consider naming repository/tooling maintenance as an additional work type.
- `docs/workflow/step2_feature_description.md`, Risks: the user's repository-creation question exposed a concrete external dependency. The description records destination/access decisions before Step 3 and repository availability before publishing migrated material. Retain early validation with dependent-work blockers.
- `RAILSPIKE.md`, Railspike Debug Mode / Durable state and recovery: inherited enabled mode from Step 1 without consulting a project marker; retained the existing log and appended this report. Retain the recovery contract.
- `docs/workflow/step2_feature_description.md`, Completion boundary: requiring the consumer and maintainer outcomes together prevents removing development material before its preserved destination and references work. Retain the end-to-end and recovery requirements.

### Redundant/unnecessary instructions
- No supported new findings; the Step 1 finding about duplicate reprint requirements remains applicable and unchanged.

### Inapplicable instructions
- `docs/workflow/step2_feature_description.md`, Shared component inventory / UI and API surfaces: this repository has no application UI/API presenting the feature's data. The inventory instead names the canonical instructions, website, and check scripts that must be reused. Clarify that non-application work should inventory its existing reusable artifacts.

### Uncertain assessments
- `docs/workflow/step2_feature_description.md`, Risks / mitigation before Step 3: repository identity, hosting, and migration ownership remain unresolved. Recorded these as explicit planning prerequisites, not completed checks; the current turn creates no repository or deployment. Retain the blocker rule when preparing Step 3.
- `docs/workflow/step2_feature_description.md`, Deliverable / one-page limit: the required scope, recovery, inventory, risks, and success criteria produce a dense page for this two-repository change. Kept sections concise; rendered page length has not been verified.

## 2026-10-13T07:55:52Z — Step 3

### Necessary/useful instructions
- `docs/workflow/step3_development_plan_before.md`, Before Checklist: established explicit Step 2 approval and inherited enabled state. The later user instruction named `rlspk/railspike` and `rlspk/railspike-dev`; updated Step 2's source assumption and appended that direction to Step 1 while preserving its Original Query. Retain scope reconciliation on entry and during user steering.
- `docs/workflow/step3_development_plan_do.md`, Completion Contract and Key Risks: identified a concrete old-source update guard, a fixture tied to the product README's location, and website publishing dependencies. The four-stage plan preserves development material before product removal and includes source migration and recovery verification. Retain end-to-end requirements.
- `docs/workflow/step3_development_plan_do.md`, resolve material risks before dependent work: unauthenticated `gh` blocked permission/Pages inspection. Public API reads found development public/apparently empty and product HTTP 404, which cannot establish absence. Destination names are resolved; visibility/access/hosting remain explicit execution blockers, not presumed successful checks. Retain dependency gates.
- `docs/workflow/step3_development_plan_after.md`, After Checklist: checked all six required fields in each of four stages, concise length (482 words), and whitespace; Git workflow fixture passed. The link checker reports 103 findings: this workflow contributes only three links to its unwritten Step 4 summary, with remaining findings outside this workflow. Retain checks without manufacturing future artifacts to silence expected links.

### Redundant/unnecessary instructions
- `RAILSPIKE.md`, Key Rules / Step 3 begins with Key Risks, versus `step3_development_plan_do.md`, Structure / Completion Contract then Key Risks: ordering guidance overlaps imperfectly. Used the phase file's precise ordering, keeping risks near the top. Consolidate into one canonical section order.

### Inapplicable instructions
- `docs/workflow/step3_development_plan_do.md`, database changes and function signatures: this migration requires no database or planned application functions. The plan names existing instruction, script, repository, and hosting contracts instead. Retain the conditional wording.

### Uncertain assessments
- `RAILSPIKE.md`, Step 4 commit cadence: a plan whose purpose is moving its own records spans two repositories, while the current rule assumes summary and implementation live together. The draft specifies paired stage commits and a final product commit removing its temporary summary, with the canonical summary in development recording the product commit. This proposed migration convention is reviewable in Step 3; verify it against Step 4 before execution rather than silently claiming the single-repository rule covers every transition.
- `docs/workflow/step3_development_plan_after.md`, stage sizing: four stages target one hour each, excluding external access waits. Link inventory and preservation evidence may expose greater effort; the plan requires splitting/reassessment before overrunning and does not guarantee a completed migration in four hours.
- `docs/workflow/step2_feature_description.md`, risks resolved before Step 3: destination names were supplied, but access/hosting could not be established. Produced a conditional plan with those prerequisites blocking dependent work, rather than representing Step 2's early validation as complete. Clarify whether this instruction intends to block drafting or only execution of dependent stages.
