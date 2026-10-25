# Railspike

## Overview
Planning, documentation, development, bug fixes, test suites, and checklists can use this four-step workflow, with an optional solution assessment upfront. Review and revise the current artifact before approving the next step; a planning handoff can pause before implementation. To keep the instructions inside the context window, the detailed guidance for each step now lives in separate files that you open only when you are ready for that step.

## Repository Boundary
Instruction files under `docs/workflow/` belong to the Railspike repository. If Railspike is included in another repository as a submodule or vendored directory, resolve those paths relative to the Railspike repository root, not the host repository root. Planning artifacts still belong in the host repository under `docs/plans/`.

When developing Railspike itself, use the separate `railspike-dev` checkout as the planning workspace and consuming-project root; its plans and debug logs belong there. Product edits belong in `railspike`, website edits in `rlspk.github.io`. Keep stage summaries in the development workspace and record paired implementation commits before advancing; do not add Railspike's own development records to the installable product.

## How to Use This Chain
1. Start with the highest-numbered approved step (usually Step 1 unless explicitly skipped).
2. Read the relevant instruction file in Railspike's `docs/workflow/` directory and follow the [instruction summary contract](#instruction-summaries) before starting work.
3. For Steps 3 and 4, use phase files in order: `*_before.md` -> `*_do.md` -> `*_after.md`.
4. Request approval in the format `Approved Step N` when required, and do not open the next step's files until approval is received.

## Instruction Summaries

After reading the applicable instructions and before acting, briefly summarize the next action, relevant constraints, and any approval gate. Keep the summary focused on the upcoming work rather than compressing the entire file; no separate reading acknowledgment is required.

Summarize again only when the next action, relevant constraints, or approval gate changes. A step/phase transition or resumption alone does not require repetition. On resumption, reread applicable instructions and restore workflow state; omit an unchanged summary when prior context is recoverable, or establish a fresh summary after restoration when it is not.

The original instructions remain authoritative, including exceptions omitted from a summary. Summaries never replace required reading, step/phase order, state restoration, approvals, or commit rules. If required instructions are missing or unreadable, report the blocker and resolve it before proceeding; do not imply they were read.

Do not automatically reprint instruction files. Explicit requests to show them remain supported, as do relevant quotations needed to explain a concrete decision or blocker and useful progress/handoff updates. This contract governs assistant-authored repetition, not ordinary tool-output rendering, and applies with debug enabled or disabled; summaries are not diagnostic reports.

## Step Guide
- **Step 1 – Solution Assessment (Optional)**: compare approaches, combine compatible options, and refine the recommendation before approval. `docs/workflow/step1_solution_assessment.md`
- **Step 2 – Feature Description**: capture problem framing, user stories, requirements, and success criteria. `docs/workflow/step2_feature_description.md`
- **Step 3 – Development Plan**: break work into atomic stages with dependencies and verification notes. Start with `docs/workflow/step3_development_plan_before.md`, then follow the `do` and `after` files.
- **Step 4 – Implementation**: execute the approved artifact on a feature branch and maintain the implementation summary. The artifact may be application changes or explicitly scoped documentation-only work. Start with `docs/workflow/step4_implementation_before.md`, then follow the `do` and `after` files.

Each phase file ends with instructions for when to proceed so you never overrun the context window.

## Experimental Effort Estimation

This is an optional beta capability. A user or host project may select individual cycles or enroll all future cycles in one continuing study. The consuming project's study ledger owns its candidate selection, reference set and acceptance criteria; do not embed project paths or study data in these reusable instructions. Existing approvals, documentation boundaries and commit cadence still apply. A score never authorizes implementation or expands scope.

**Activation and recovery**

- Activate when the user or host study selects the cycle, including standing enrollment of all future cycles; do not ask for selection again under that policy. In its first artifact, record `Effort study: <study/candidate ID>` and a relative link to the host ledger below the Plan navigation/debug state; inherit this field into subsequent artifacts. Record the standing enrollment policy when used. Enrollment authorizes collection, not feature implementation.
- On step entry, resumption and handoff, restore selection, the latest snapshot, scope version and frozen references from the current artifact and ledger. Unselected cycles require no score, extra field or ledger update. An absent field is not opt-out evidence when the ledger already selects the cycle; resolve conflicting selection before rating.
- If a reference is missing or its content hash differs, restore the recorded source or explicitly version an accepted replacement before rating. Do not silently reset the unit or manufacture a score. Missing historical checkpoints stay missing; skipped Step 1 is not applicable, not zero. Any later reconstruction is explicitly retrospective.
- Recover frozen sources using the [host-local reference procedure](docs/effort-estimation.md#recovering-frozen-references): resolve ledger-relative paths, verify expected hashes, and retain exact historical bytes with provenance inside the host project. A changed current document is not the frozen source. Once recovered, use the verified local copy without requiring the original external checkout; record recovery now and preserve earlier missing checkpoints.

**Score semantics and evidence**

- Use the study's frozen references with **1.0 = the largest well-scoped, releasable slice we would comfortably approve for one Railspike cycle, including required verification and documentation**. Nonnegative decimals are freeform. Scores above 1.0 prompt a split discussion, not an automatic cycle count.
- Each whole-cycle projection estimates total work for the scoped cycle from its starting point: inspection, planning, implementation, required verification, documentation and ordinary correction. It is not remaining effort, hours, priority, an approval, measured actual effort or an additive delivery forecast. Do not derive it from lines, stage counts or commit timestamps.
- Preserve inherited estimates separately and record prior exposure. Claim independent ratings only when independently collected before discussion; otherwise identify single-rater/exposed judgments honestly. Record active-work measurements only when reliable, separately from scores.
- Keep checkpoint snapshots in their step artifacts, with a comparison index in the host ledger. Each snapshot records study/candidate ID, checkpoint, UTC date, rater, score, scope version (including starting revision, outcome and recovery), reference version, exposure and reason for change. Explicitly reaffirm unchanged values. Append revisions and retain original scope/scores and approval context; distinguish new understanding from changed scope.

**Extended estimates:** [Option and stage estimates](docs/effort-estimation.md#extended-estimates) default to enabled for new enrolled effort-study cycles. Study enrollment remains optional; unselected cycles require no estimates or extra mode question. Resolve the latest explicit user override, then recorded cycle state, then applicable host policy, then the new-cycle enabled default. Record `Extended estimates: enabled` or `Extended estimates: disabled` below the study field and inherit it through subsequent artifacts. Preserve existing disabled cycles. For older resumed cycles without a mode field, recover prior requests/policy and prior behavior; do not apply the new-cycle default retroactively. See the guide for legacy recovery and explicit prospective activation. Retain earlier history when changing mode; never backfill missing historical estimates.

When enabled, every Step 1 option gets a complete scoped-cycle estimate; every Step 3 stage gets a separately labeled **stage work** estimate using the reference yardstick. Step 4 preserves originals, appends material whole-stage revisions and records separate retrospective assessments. Stage work covers only that stage's changes, verification, documentation and ordinary correction, not the cycle's planning again. Keep shared overhead explicit, cycle totals independently judged, and stage annotations separate from cycle snapshots and outcome counts. Never sum stage or alternative estimates, normalize them into fractions, or interpret retrospective ratings as measured effort. This extension leaves the frozen R1 definition and ordinary approval/commit requirements intact.

**Visible estimates:** Put a standalone bold `Estimate: 0.35` line directly beneath each estimated option/stage heading, with at most a short comment. Show `Cycle estimate: 0.60` near the top of each enrolled artifact, below its state fields. Use plain numbers without approximation signs; keep drivers, uncertainty and study metadata separate. Tables use a dedicated estimate column. Preserve ranges, unavailable reasons and explicit original/revised/retrospective labels under the [presentation rules](docs/effort-estimation.md#estimate-presentation). Disabled extended mode omits option/stage estimate fields; enrolled cycles still retain whole-cycle checkpoints.

**Checkpoints**

| Checkpoint | Required record for selected cycles |
| --- | --- |
| Intake | Preserve initial scoped estimate in the ledger or first artifact before detailed implementation inspection; disclose earlier inspection instead of pretending it was prospective. |
| Step 1 handoff, if used | Projected total for the recommended scoped approach. |
| Step 2 handoff | Projected total for defined outcome, scope and recovery. |
| Step 3 handoff | Projected total informed by planned implementation and verification. |
| Step 4 entry | Before implementation, preserve or explicitly reaffirm the Step 3 projection in the summary created after the planning commit. |
| Step 4 discoveries/revisions | Append a revised total when warranted, before dependent work where possible; changed scope still requires renewed approvals. |
| Step 4 closeout | Separately labeled retrospective scope assessment, verification/omissions and maintainer comfortable-fit judgment. Never call this a prospective score or measured actual. |

Before each planning handoff, capture the applicable snapshot and link it from the ledger when that write is authorized. Do not duplicate snapshots merely because a phase resumes. Include a brief projected-total statement in the normal handoff for selected cycles. Scope ledger updates into that cycle's approved documentation boundary; pending planning updates remain uncommitted and accumulated outcome updates belong in its closeout commit. Never bypass the planning-commit file gate to commit a ledger early. If ledger edits are outside the current scope, retain the artifact snapshot and record the pending ledger update until authorized.

At closeout, retain delivered scope, starting/final revisions, commits/diffs, planned/completed stages, verification and omissions, corrective work versus new requests, splits and the maintainer judgment. If that judgment is unavailable, mark study acceptance pending rather than inventing it; technical cycle completion and study outcome acceptance are distinct. Keep original scope/estimate when splitting and follow the host study's explicit outcome-counting rules; do not silently count child cycles as independent observations. Continue collection beyond review batches; six accepted outcomes are a review checkpoint, not a stopping rule. Version reference changes without erasing old scores.

**Continuing collection**

- Use the [bundled R1 references and record template](docs/effort-estimation.md) when starting a host study. Keep study data in the consuming project, outside the installed product, regardless of debug mode.
- Give each cycle a stable project/cycle ID; preserve legacy candidate IDs and parent/replacement links. Copies in other checkouts and worktrees are the same observation. Distinct follow-up cycles get distinct IDs with their relationship retained.
- Enroll at the first artifact and retain paused, abandoned, replaced and incomplete cycles as well as successes. On resumption of older work, collect from the current checkpoint with prior exposure disclosed; never backfill a prospective estimate. Do not require scores for small tasks that do not use Railspike.
- The host ledger indexes canonical artifact snapshots. Merge worktree records by cycle ID and checkpoint, retaining conflicting observations for review; do not allocate sequential IDs independently in parallel worktrees. No automatic upload or cross-repository write is implied.

## Railspike Debug Mode

Debug mode is optional feedback for improving Railspike's instructions, not application debugging. New workflows default to disabled unless the consuming project opts in. Enable or disable it for a workflow with a plain-language request such as “Enable Railspike debug mode for this workflow” or “Disable Railspike debug mode.”

**Project default**:
- An optional `.railspike_debug_on` file at the consuming-project root enables debug by default for new workflows. Only file presence matters: do not read or validate its contents. Empty, arbitrary, or “false” contents all enable the default; unreadable contents do not matter when file presence is established. An absent marker leaves the default disabled.
- Use the consuming-project root established for the workflow and its `docs/plans/`, not the current shell directory or an installed Railspike directory. For work on Railspike itself, this is the separate `railspike-dev` planning workspace root; for submodule or vendored installations, it is the host project root. Do not search ancestor directories or apply nested-project or user-global inheritance.
- Consult the marker only for a new workflow without an explicit mode request. If the consuming root or marker's file presence cannot be established, ask for clarification instead of assuming absence. A directory at the marker path is not a marker file; clarify that mismatch when lookup is needed.
- Record the resolved mode in the first artifact as a snapshot. Adding or removing the marker affects future workflows only; editing its contents has no effect. Workflow-specific overrides do not create, remove, or edit the marker.

**Durable state and recovery**:
- Record `Debug mode: enabled` or `Debug mode: disabled` immediately below the current artifact's Plan navigation bar; inherit it into subsequent artifacts, including the Step 4 summary. If no artifact exists, record it when creating the first one.
- On step entry, resumption after context loss, and before a completed-step handoff, read this contract and the current artifact's field. If the next artifact does not exist, inherit from the latest completed artifact. Historical fields are snapshots, not competing current settings.
- Resolve mode in this order: latest explicit user enable/disable request, existing workflow state, project default for a clearly new workflow, then disabled when no marker exists. Update the current field for an explicit request. For resumed work, ask for clarification when available evidence cannot resolve missing or conflicting state; never use the project marker to repair uncertain resumed state or silently reset it.
- Mode changes do not approve steps or authorize advancing, branching, or committing. During Step 4, record changes in the summary and include them in the next authorized stage commit; never amend completed commits.

**Completed-step report**: When enabled, save the complete diagnostic report in the debug log. In each completed Step 1–4 handoff, include exactly one short debug line linking to the saved log, before requesting approval where applicable. Do not repeat findings, group headings, or empty-group markers in the conversation, or narrate diagnostic collection. Phases and implementation stages do not trigger reports. When disabled, emit no diagnostics or debug link and preserve existing logs.

**Conversation exceptions**: Briefly disclose log-write failures or request clarification when available evidence cannot resolve mode state. Provide findings in the conversation when the user explicitly requests them. Do not dump unsaved diagnostics into the conversation as a fallback for a failed write. Ordinary task updates, blockers, approval requests, and the instruction summary contract remain unchanged.

**Full report content (log only)**:

- Always include **Necessary/useful instructions** and **Redundant/unnecessary instructions**; use “No supported findings” for an empty group.
- Each finding identifies its Railspike source (file and section or short excerpt), observable contribution or overhead in this step, and a justified suggestion to retain, clarify, consolidate, or remove it.
- Put relevant **Inapplicable instructions** and **Uncertain assessments** in distinct groups. Non-use alone does not establish redundancy. Report selectively, without claiming exhaustive coverage or access to hidden reasoning.
- Findings are advisory: continue following required instructions and approval gates. Changing Railspike's instructions requires separately authorized work.

**Persistent debug log**: Before linking to a new report or presenting explicitly requested findings, append the full report to `{feature_name}_debug_log.md` beside the planning artifacts. Create it on the first report and reuse it across steps, resumptions, and mode changes. Every entry has a UTC timestamp and step identifier. Never overwrite entries: append corrections labeled `Revision`, identifying the superseded entry; skip unchanged reports and link to the existing log without claiming a new entry was saved. If writing fails, briefly report the failure rather than claiming the diagnostics were saved; resolve the failure before presenting output as logged.

Move the log with the plans into `docs/plans/{feature_name}/` and repair links without altering mode state or log history. Keep it uncommitted during Steps 1–3; include this feature's existing log in the initial planning commit. During Step 4, include additions in the next authorized stage commit, or make a separate log-only handoff commit after the final stage for the completed-step report. This narrow allowance does not authorize unrelated changes or replace stage commits. Do not amend completed commits.

## Planning Artifacts
Each step MUST be a separate file in `docs/plans/`:
- **Step 1**: `{feature_name}_step1_solution_assessment.md`
- **Step 2**: `{feature_name}_step2_feature_description.md`
- **Step 3**: `{feature_name}_step3_development_plan.md`
- **Step 4**: `{feature_name}_step4_implementation_summary.md`

**Directory structure and organization rule**: After explicit `Approved Step 3` and creation or eligible reuse of the Step 4 feature branch, organize the current feature's planning artifacts in `docs/plans/{feature_name}/` before this cycle’s planning commit or implementation, regardless of artifact count or whether Step 1 was skipped. Reuse an existing feature folder. Preserve filenames, separate step files, and approved substantive content. Repair relative plan navigation and affected repository references; add or update this feature's entry in `docs/plans/README.md`, creating the index if absent.

The initial planning commit contains only approved Steps 1–3 (Steps 2–3 if Step 1 was skipped), this feature’s existing debug log if present, and the moves, index entries, and reference fixes necessary for this feature’s organization. Exclude implementation, the Step 4 summary, unrelated plans, and other unapproved auxiliary content. This narrow organization allowance qualifies the [Step 4 planning-commit gate](./docs/workflow/step4_implementation_before.md#planning-docs-commit-gate-required); it does not authorize substantive revisions to approved plans. Create the Step 4 summary in the same folder only after the planning commit, inheriting debug state under the [debug recovery rules](#railspike-debug-mode). Organization must not change that state.

Inspect destinations and affected references before moving files. If files conflict, the destination is ambiguous, or organization requires substantive changes, stop and resolve the issue before committing or implementing. Do not overwrite artifacts or silently revise approved scope; seek renewed approval for substantive changes.

**Plan navigation**: Start every artifact with this relative-link bar; omit Step 1 only when skipped.

```md
> **Feature plan:** [Step 1](./{feature_name}_step1_solution_assessment.md) · [Step 2](./{feature_name}_step2_feature_description.md) · [Step 3](./{feature_name}_step3_development_plan.md) · [Step 4](./{feature_name}_step4_implementation_summary.md)
```

### Agent attribution

Sign beneath each authored or revised option, stage or other substantive plan section in Steps 1–4. Use one short italic attribution line per coherent contribution, not per bullet. A compact single-contribution artifact may use one footer. Attribution applies independently of debug mode and effort-study enrollment.

For Step 3, when one agent generates the entire plan in one pass, use a single attribution footer for the whole plan, regardless of plan length. Use stage-level attribution only for stages subsequently authored or substantively revised separately. Preserve the original plan footer and prior stage attribution when recording revisions.

Use the agent's known name and UTC date. Include the model name/version and relevant settings (for example reasoning effort or temperature) **when verified for the session that produced that contribution**. Use only explicit, available runtime/session metadata; a configured preference is not proof of the actual runtime model. Omit unknown fields, or mark them unavailable once in shared metadata. Never infer them from the agent name, output style, Git author, another agent or an example. Do not delay work or ask the user merely to fill optional fields. Record only shareable metadata, not credentials, hidden prompts or private configuration.

Minimal form: `*— Agent name · YYYY-MM-DD UTC*`. With verified metadata: `*— Agent name · YYYY-MM-DD UTC · Model: <verified model> · Reasoning effort: <verified setting>*`. Include other relevant verified settings as named fields; omit unavailable ones rather than copying placeholders. Examples are formatting illustrations, not evidence of a live model or setting.

Preserve prior attribution when revising another agent's work; append `*— Revised by Agent name · YYYY-MM-DD UTC*` beneath the changed contribution, with verified model/settings if available. Preserve earlier dated entries for later revisions, including changes of model/settings by the same agent. Attribute only work actually authored or revised; a reviewer or agent merely copying an earlier estimate does not become its original author/rater. Do not backfill unknown historical authorship. These are textual authorship records, not cryptographic signatures, approvals or independent ratings.

**Commit discipline**:
- Keep Step 1-3 planning documents uncommitted while they are being drafted/revised.
- Do not commit Step 1-3 planning documents when Step 1 or Step 2 is approved.
- After the user explicitly responds `Approved Step 3`, create the Step 4 feature branch or confirm eligible reuse under [Follow-up Cycles Before Merge](#follow-up-cycles-before-merge).
- Before this cycle’s planning commit on that branch, organize the plans under the rule above; limit the commit to approved planning documents and its organization allowance.
- During Step 4, each completed stage must be committed with its Step 4 summary update in the same commit before starting the next stage.

**Plan review**: Plans are working documents. The user may edit the current artifact or request revisions, including a combination of compatible Step 1 options. Recheck tradeoffs and scope after revisions; a revision request is not approval to advance. Do not begin Step 4 until the user explicitly responds `Approved Step 3`. Organize and commit the approved plans under the organization rule above before implementation.

**Step 4 commit cadence (mandatory)**:
- Make one planning commit at the start of Step 4 containing approved plans and only the organization allowance above.
- Then make at least one stage-scoped artifact commit per Step 3 stage.
- Do not start Stage `N+1` until Stage `N` has:
  - applicable verification completed,
  - Step 4 summary updated for that stage,
  - a commit recorded on the branch.
- Do not squash/rebase/amend stage commits during active Step 4 execution.
- Expected minimum commit count by end of Step 4: `1 + (# of Step 3 stages)`.

**Documentation-only scope**:
- Documentation-only work is permitted only when Step 2 names it as the work type and names the allowed documentation file scope; Step 3 must retain that boundary in its Completion Contract.
- Branching and commit cadence always apply. Documentation-only verification is proportional to the approved artifact: document integrity, evidence, links, and authorized-file-scope checks are required; runtime, UI, deployment, migration, and release checks are not applicable unless the approved documents make a claim that requires one.
- Do not alter application source, tests, CI, deployment configuration, generated artifacts, or other files outside the approved documentation scope. Return to Step 2/3 for approval if such a change becomes necessary.

## Key Rules

**AI coding agent**
- Recommend Step 1 for complex features or whenever multiple solutions exist
- Stay in the current step; do not draft/edit later deliverables without approval
- After delivering each step, explicitly request “Approved Step N” and pause until the user responds with that exact phrase
- Create separate files for each step only after receiving the relevant approval
- ALWAYS establish a feature branch before Step 4 implementation; reuse only under [Follow-up Cycles Before Merge](#follow-up-cycles-before-merge)
- Enforce Step 4 commit cadence: first organize and commit approved plans under the organization rule above; each completed stage has a stage-scoped commit that includes the Step 4 summary update
- Report Step 4 checks as passed, failed, blocked, pending, or inapplicable; a focused pass is never an unqualified full-suite or user-outcome result
- Treat documentation-only work as a Step 4 implementation only when its allowed documentation file scope was approved in Steps 2 and 3; use applicable verification and record non-applicable runtime checks in the summary
- Prefer shared components/API contracts first; reuse or extend instead of forking markup, CSS, or payloads
- Apply [Enhancement Requests](#enhancement-requests): document every request, incorporate only in-scope refinements, and replan changed scope
- A feature is a releasable vertical slice: normal entry, end-to-end outcome, and required recovery. Component-only work is internal maintenance; split larger stories vertically.
- Keep work within a day or eight Step 3 stages; otherwise rescope the slice.
- Avoid database schema changes when possible—lean on existing models/fields
- Read the current step/phase instructions and apply the [instruction summary contract](#instruction-summaries) before acting
- Add the Plan navigation bar to every Step 1–4 artifact
- Step 1 starts with `## Original Query`: preserve the request except mechanical grammar, spelling, capitalization, punctuation, and formatting fixes; when needed, follow it with a brief, clearly labeled `## Understood Intent` that clarifies inferred goal/context without inventing scope
- For Step 3, prefer `## Stage N` headers with flat bullet lists for each stage field so plans stay easy to scan and review
- When the request names a known user or environment, Step 2 states that user's ordinary entry and recovery condition; evidence from another supported platform never satisfies it
- Step 2 risks state impact, early validation, and mitigation; Step 3 begins with `## Key Risks`, and unresolved risks block dependents
- For Step 4 summaries, prefer `## Stage N - title` headers with bullet lists for changes, verification, and notes so stage handoff stays easy to audit

**User**
- Review, revise, and approve explicitly at each step; question assumptions and combine compatible options before settling on a direction
- Flag issues early so adjustments happen before implementation
- Resist adding scope during Step 4
- Prefer solutions that avoid database migrations; rely on existing schema where feasible

## Follow-up Cycles Before Merge

Completed Step 4 means the approved cycle is complete, not necessarily ready to merge. Related enhancements for the same intended release may use a distinct follow-up cycle on the same unmerged feature branch when the user requests reuse. Confirm the branch is still unmerged; if eligibility is uncertain, clarify before reuse. Merged branches are ineligible: create a new feature branch.

Give each follow-up its own descriptive feature prefix (for example, `search_filters` following `search`) or a unique numbered fallback (`search_cycle2`), independent of branch name. Check for collisions before writing; never overwrite another cycle's artifacts. In the follow-up's first artifact, link the predecessor and record the intended reused branch; inherit this cycle identity into later artifacts and restore it on resumption. Keep the predecessor's completed content intact; record requests and backlinks separately when necessary.

Use fresh approvals for this cycle (Step 1 optional). After `Approved Step 3`, create a new branch or confirm the explicitly requested eligible branch reuse, then organize this cycle's plans and make its own planning commit before implementation. Create its summary afterward. Each cycle retains one planning commit plus at least one stage-scoped commit per stage, with stage-summary updates; prior cycle commits and approvals do not count. Count from this cycle's planning commit, not the branch's creation. Branch reuse does not authorize merging, publishing, or rewriting completed history.

## Enhancement Requests

Record every enhancement request before acting in the current planning artifact or Step 4 summary. Use a concise record: **Request / Disposition and reason / Approval status / Outcome or follow-up link**. Keep deferred and declined requests visible; conversation and commit messages alone are insufficient. An implemented request must identify changes, verification, and its stage commit. Record the commit after creation without amending it; include the reference in the next authorized summary update.

Classify against approved requirements, file boundaries, dependencies, risks, and completion criteria, not estimated effort:
- **In-scope refinement:** incorporate within the approved current stage and record verification. Adjusting copy in an approved UI stage can qualify; adding an export format does not.
- **Changed scope:** preserve completed work, return to the earliest affected planning step, and obtain renewed approvals before implementing the changed scope. During planning, revise the current artifact; a revision request never approves a step.
- **Separate work:** retain a pending request or follow-up link and continue the original task unless the user asks to stop or switch. Do not silently start deferred work.
- **Ambiguous:** clarify before dependent work; continue independent authorized work when possible.

On resumption, recover pending requests, their approval status, and the active cycle from artifacts. Resolve missing or conflicting state before dependent work. Preserve completed substantive records and commit history; record later dispositions separately rather than rewriting completed scope.

## Warning Signs
- **Step 1**: >1 page, >4 options, or verbose explanations
- **Step 2**: >1 page, code/DB details, mockups, buried risks, or a component-only "feature"
- **Step 3**: >1 page, stages >2 hours, tangled dependencies, missing Completion Contract/Key Risks, unusable outcome, or incomplete risk details
- **Step 4**: Missing branch/planning commit/stage commit + summary, scope changes, direct-only behavior, or too few commits

## Workflows
- **Simple**: Step 2 → Step 3 → Step 4 (create or eligible reuse of feature branch → implement stages → test/commit → complete)
- **Complex**: Step 1 (solution assessment) → Step 2 → Step 3 → Step 4
