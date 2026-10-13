> **Feature plan:** [Step 1](./separate_development_content_step1_solution_assessment.md) · [Step 2](./separate_development_content_step2_feature_description.md) · [Step 3](./separate_development_content_step3_development_plan.md) · [Step 4](./separate_development_content_step4_implementation_summary.md)

Debug mode: enabled

## Problem
Railspike installations include its own development material, cluttering consuming projects. Approved Step 1 selects a lean product repository and a companion repository for development. After Step 2 approval, the user specified `https://github.com/rlspk/railspike` for the product and `https://github.com/rlspk/railspike-dev` for development; this supersedes the original assumption of retaining the installation URL.

## User stories
- As a project developer, I want only usable Railspike product files so that upstream development records do not clutter my project.
- As a maintainer, I want preserved records and working checks so that separating the product does not disrupt development.

## Core requirements
- Use `rlspk/railspike` as the product and installation source, with `RAILSPIKE.md`, `WELCOME.md`, workflow instructions, recovery guidance, user documentation, and licensing usable independently; document the transition from `gulkily/railspike`.
- Move upstream plans/logs, maintainer records, research, development checks, and website sources to the companion repository; retain discoverability, attribution, and recoverable originals.
- Keep the complete-product copy contract and explicit submodule option. Host-project plans remain in the host's `docs/plans/`; consuming projects must not need the companion repository.
- Give maintainers one canonical home for future Railspike plans and checks, including this active workflow after migration; preserve debug history and step/commit discipline.
- Document updates from existing installations, preserving local edits and rollback. Do not rewrite history or automatically convert installations; old Git history may still contain development files.

## Delivery scope
**Work type: application change**, specifically product distribution and repository maintenance, not documentation-only. Scope includes product guidance, relocation of development material and website assets, adapting existing checks, and the hosting transition needed to preserve website access. No workflow redesign, new application runtime, or automatic publishing system. Unrelated untracked files require an explicit inventory/disposition before migration.

## Completion boundary
Deliver a usable lean product and a verified companion copy before removing development files from the product. A new consumer can install, complete welcome, and create its own plan; maintainers can locate records and run checks. Release requires both repository states to be available, links/website access verified, and recovery instructions supplied; a partial migration must retain recoverable source material.

## Risks
- **Destination/access:** destinations are now user-specified; missing access blocks migration. Public API inspection found `rlspk/railspike-dev` public and apparently empty, while `rlspk/railspike` returned 404; local GitHub CLI authentication is absent. Confirm product visibility/access and inspect both destinations before publishing; do not infer that 404 proves absence.
- **Broken links/website:** relocation can strand users. Before Step 3, inventory references and establish the hosting transition; repair live links and document historical references. Unresolved hosting blocks dependent removal.
- **Lost work/ownership:** active plans and local edits can diverge. Before Step 3, inventory tracked/untracked work and define the cutover; verify preservation before deletion and keep rollback available.
- **Scope growth:** coordinated migration may exceed one day/eight stages. Validate feasibility before Step 3; rescope explicitly rather than declaring a partial split complete.

## Shared component inventory
Reuse `RAILSPIKE.md`, `WELCOME.md`, `docs/workflow/`, and `docs/failure-modes.md`; adapt README, documentation index, and contribution links. Relocate the existing website and all three link-checker variants plus the Git-workflow check. No application UI/API surfaces or replacement workflow engine are needed.

## Simple user flow
1. Obtain Railspike from `rlspk/railspike` by copy, clone, or submodule; existing users follow the documented source transition.
2. Follow welcome and write plans in the consuming project.
3. Follow a maintainer link only when development records or checks are needed.

## Success criteria
Fresh installations contain zero upstream development records or tooling; all three installation forms retain required product files; a host-plan walkthrough succeeds without the companion checkout; migrated records are accounted for, live links and checks pass, and an existing-installation update demonstrates preservation and recovery.
