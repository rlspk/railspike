# Project concept inventory

Keep a concise inventory in the consuming project's `docs/concepts/`, outside the installed Railspike directory. This is ordinary workflow documentation: no flag or activation prompt. Grow it only as cycles touch concepts; do not survey the project, audit the whole inventory, or backfill old plans.

A concept is a coherent piece of behavior with a purpose, such as voting or reservations. Use this as a planning lens even when code boundaries are untidy; it does not require independent services or declarative synchronizations. Do not invent concepts for work that has none.

## Entries

Use one Markdown file or several, grouped for readability. Reuse existing entries and preserve unrelated content. Keep each entry to:

- Name and one-line purpose.
- A brief behavioral scenario (operational principle) showing how it serves that purpose.
- Relevant source or instruction paths.

Describe current behavior. Label uncertainty and proposed behavior explicitly; a proposal is not evidence of implementation. An operational principle illustrates behavior, not a replacement for acceptance or recovery criteria.

## Planning

Read relevant existing entries and include **Concepts touched** in each new or revised plan: names, links to existing entries, and whether each is created, changed, or used unchanged. Mark missing entries as proposed instead of linking to nonexistent files. Say “none” when appropriate. Step 1 may list candidates by option; Steps 2 and 3 refine the chosen scope. A one-shot record carries the equivalent list.

Identify needed inventory additions or corrections in the plan, within its approved documentation scope. Keep proposals in the planning record until implementation; do not create the inventory just because planning began. Existing scope and approval rules still govern the work.

## Implementation and verification

Create or update only entries touched by the authorized cycle, including missing descriptions of concepts used unchanged. Keep entries aligned with delivered behavior and include updates with the corresponding work under the existing commit rules; use linked commits when product and development records occupy separate repositories.

Verify touched entries and their paths against the resulting code or instructions. Correct mismatches within scope, distinguishing an inaccurate description from a behavior defect; changing the inventory does not authorize changing behavior. Leave unrelated entries alone and report unresolved uncertainty. When no concept is relevant, no inventory file is needed.
