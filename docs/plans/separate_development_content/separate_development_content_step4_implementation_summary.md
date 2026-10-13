> **Feature plan:** [Step 1](./separate_development_content_step1_solution_assessment.md) · [Step 2](./separate_development_content_step2_feature_description.md) · [Step 3](./separate_development_content_step3_development_plan.md) · [Step 4](./separate_development_content_step4_implementation_summary.md)

Debug mode: enabled

## Stage 1 - Preserve the maintainer workspace
- Changes: Created the companion checkout at `/home/wsl/railspike-dev` from tracked development material; preserved license, source revision, and SHA-256 inventory in `docs/maintainers/separation_manifest.json`. Product history remains intact. Unrelated untracked and ignored files were excluded.
- Verification: Both destination repositories are public and had no refs; Git push dry-runs passed. Every migrated file matched its source hash. Recovery bundle and untracked backups: `/home/wsl/railspike-separation-recovery-20261013T080640Z`.
- Notes: Git transport works, but GitHub API authentication returns 401; Pages configuration remains a Stage 2 prerequisite. Companion publication is pending. Development becomes the canonical home for plans after publication verification.
