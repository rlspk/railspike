> **Feature plan:** [Step 1](./separate_development_content_step1_solution_assessment.md) · [Step 2](./separate_development_content_step2_feature_description.md) · [Step 3](./separate_development_content_step3_development_plan.md) · [Step 4](./separate_development_content_step4_implementation_summary.md)

Debug mode: enabled

## Original Query
Split Railspike development content from Railspike itself so that we don't clutter the repo we're cloned into. Write Step 1 and use debug mode.

## Understood Intent
Keep Railspike's own development records out of consuming projects while retaining the complete usable workflow. Treat “cloned into” as including direct clones and submodules, alongside the current default copy installation; retain development material for maintainers.

## Problem
The current repository bundles product instructions with upstream plans, debug logs, maintainer documents, checks, and website assets, and installation carries that development material into consuming projects.

## Option A — One repository, minimal distribution
Keep development in this repository but define a self-contained product distribution for copying into projects, containing the workflow, welcome, user guidance, and license.

- **Pros:** One development history; no repository migration; copied installations become smaller.
- **Cons:** Ordinary clones and submodules still include development content; distribution boundaries and links need ongoing verification.

## Option B — Product repository and companion development repository
Keep the existing Railspike repository as the complete user-facing product; move Railspike's plans, debug logs, maintainer records, development checks, and website sources to a companion development repository with clear ownership.

- **Pros:** Copies, ordinary clones, and submodules all get a lean product; development records remain available without entering host projects.
- **Cons:** Cross-repository references, validation, and website publishing need coordination; historical links and ongoing plans need a migration policy. Existing Git history still contains old development material.

## Option C — Development repository with a published product repository
Keep the current repository for development and publish only the consumable product into a separate repository used for installation.

- **Pros:** Preserves the current development context; product clones and submodules contain only the published workflow.
- **Cons:** Changes the installation source; adds publishing and synchronization work, with a risk of stale product releases.

## Recommendation
Choose **Option B** if ordinary clones and submodules must be clean: it preserves the existing installation source and addresses all supported installation forms. Choose **Option A** if reducing default copied installations is sufficient; merely moving development into another folder does not meet the broader goal.

The first vertical slice should let a user obtain the lean product, complete welcome, and write a host-project plan, while maintainers can find the preserved development records and validate the product. Include update/recovery guidance for existing installations without discarding local edits. Before detailed planning, settle the companion destination, file boundary, active-plan ownership, and website/check ownership; preserve licensing and usable links. Exclude history rewriting, automatic publishing, and automatic conversion of existing installations. Aim for one day or at most eight stages; split broader infrastructure migration into a follow-up if needed.

## User-specified destinations after Step 2 approval
Use `https://github.com/rlspk/railspike` for the product and `https://github.com/rlspk/railspike-dev` for development. This retains Option B's separation but supersedes its assumption of an unchanged installation URL; include an explicit transition from `gulkily/railspike` while preserving local edits and provenance.
