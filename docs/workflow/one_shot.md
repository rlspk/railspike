# One-shot cycles

Use this workflow after reading [Railspike's mode selection](../../RAILSPIKE.md#choose-the-execution-mode). One-shot execution reduces handoffs while retaining the substantive evidence of a staged cycle. It does not mean undocumented work or a single tool call.

## Entry and authorization

1. Read applicable project instructions, including `AGENTS.md`. Resolve missing or unreadable required instructions before dependent work. Identify the host repository and preserve unrelated local work.
2. Establish explicit user authorization for bounded one-shot execution, the intended outcome, and exclusions. “Implement this fix as a Railspike one-shot” can authorize execution when the fix's boundary is clear. “Write a plan,” a reference to a plan, or a question about implementation cannot. Do not ask again when the existing request already supplies clear authority; resolve only material ambiguity.
3. If the approach, scope, or risk needs review before execution, use staged planning. Do not switch an active staged cycle into one-shot mode merely because a later request sounds small; obtain explicit authorization for the mode and scope change, retaining its history.
4. Before implementation, create a distinct cycle record at `docs/plans/{feature_name}/{feature_name}_one_shot.md` in the host. Check for collisions; resume the same cycle's record when appropriate, never overwrite unrelated work. Add its link to `docs/plans/README.md`, creating the index if needed. Record original request, actual authorization, bounded outcome, approach, risks, verification and recovery expectations. Keep detail proportional; do not invent alternatives or stages.
5. Resolve and record debug and study state under the shared policies. Establish a feature branch before implementation; reuse an unmerged branch only on explicit user request under the shared follow-up eligibility rules. A new follow-up has its own record and predecessor link.

For documentation-only work, record the authorized documentation paths and intended reader outcome before editing. Do not change application source, tests, CI, deployment, or generated files under documentation-only authority. Check document integrity, evidence, links and file scope; mark runtime checks inapplicable unless a document claim requires them.

Include **Concepts touched** and proposed inventory additions/corrections in the record's bounded scope, following [concept guidance](../concepts.md#planning).

## Execution and evidence

Maintain and verify touched inventory entries with the authorized work using [concept guidance](../concepts.md#implementation-and-verification).

Work within the recorded authority. Preserve the original request/scope and append dated decisions, discoveries, scope changes, and authorization evidence. Record every enhancement request with disposition, reason, approval status, and outcome or follow-up link, using the shared enhancement classification. Distinguish corrections from additions. An agent-written record is evidence of a claim, not independent proof of user approval.

Answering a question does not increase authority or automatically revoke permission already granted. If work exceeds the boundary, stop dependent implementation and seek renewed bounded authorization or transition to staged planning. Do not perform the expansion while asking for approval. Retain still-valid work and unrelated local changes.

Run checks appropriate to the outcome and capture commands, results, omissions and recovery instructions. Label checks passed, failed, blocked, pending, or inapplicable. A focused check does not establish a full-suite pass or success in an untested environment. Record technical status separately from commit, merge and publication status. Keep incomplete, paused, failed and abandoned cycles visible.

## Resumption and scope changes

On resumption, reread applicable instructions and this record. Restore cycle identity, mode, branch/revisions, actual authorization, latest scope, pending requests, verification status, and study/debug state. Compare the working tree with recorded work; do not discard unexplained differences or infer permission from their presence. If authority or state cannot be recovered, identify the missing evidence and clarify before dependent work. Preserve failed attempts and corrections rather than rewriting the record as if they never happened.

For renewed one-shot authorization, append the changed scope and user's instruction before executing it. If staged review is needed, retain the original record, mark its transition, and start the earliest affected planning step (Step 1 for approach uncertainty, otherwise Step 2). Link both directions and obtain normal staged approvals before further implementation; one-shot authority does not approve the new plans. Preserve existing implementation and commits separately from the new planning-only commit. For the same cycle, retain its identity, study history, scope versions, and debug log. The approved staged scope must identify retained work and remaining work. An existing unmerged feature branch can continue for the same cycle; record that continuation, rather than treating it as a new follow-up branch reuse. Do not reuse a merged branch for further implementation.

Separate additional work receives a distinct linked identity and its own authorization. Do not count a mode transition, superseded artifact, or worktree copy as another study outcome. Related split cycles follow the host's outcome-counting rules. Preserve paused/abandoned status and unresolved requests even when execution ends without success.

## Study and debug state

Use the host's enrollment policy, independent of debug state. For enrolled cycles, follow [one-shot effort checkpoints](../effort-estimation.md#one-shot-checkpoints); unselected cycles omit study fields and estimates. Missing intake stays missing rather than being reconstructed after work starts. Restore prior values on resumption and append material revisions before dependent work where possible.

Apply shared debug precedence and report content. Put the debug field near the top of the record, below its cycle/index line. When enabled, append a complete diagnostic report to `{feature_name}_debug_log.md` beside the record at closeout, including a paused, failed, abandoned, or staged-transition handoff. Each report has a UTC timestamp and lifecycle identifier; unchanged resumptions require no duplicate report. Include exactly one short debug link in the handoff. Keep full findings in the log. Disabled cycles produce no diagnostics or debug link and preserve existing logs. A failed write must be disclosed and resolved before claiming a report was saved.

Include enabled log changes in the next authorized one-shot commit; after the final commit, a log-only handoff commit is permitted. Explicit no-commit requests apply to logs too. On transition, inherit resolved debug state and continue the same log under staged cadence; never use a new project-marker lookup to overwrite resumed state.

## Commits and closeout

One-shot cycles do not require a separate planning commit or fabricated stage commits. Normally make one completion commit containing only the bounded changes, updated record, relevant index/ledger updates and existing debug log. Additional meaningful commits are allowed; do not rewrite completed history to improve appearances. Verify and inspect intended files before each commit. An explicit no-commit request takes precedence: leave changes uncommitted and report that status.

For separate product/development repositories, commit each repository's authorized files separately and keep the host record linked to the paired revisions. Do not put development records inside the installable product. One-shot authorization does not grant merge, push, tagging or release permission.

A record cannot contain the hash of the commit that first contains it. Before that commit, mark its reference pending. After creation, confirm the revision with Git and append it in the next authorized record update without amending the commit. If no further work remains, one record-only handoff commit is allowed for the confirmed implementation references; report that handoff commit's own hash in the final response without creating an endless record/commit chain. If commits are prohibited, retain the reference update uncommitted. Never invent a hash or treat a pending reference as missing implementation.

At closeout, record delivered outcome, verification limitations, recovery/next action, unresolved requests, commit status and applicable study closeout. Sign authored contributions under the shared attribution rules. Report concise results, with the record link and any required debug link. Do not declare completion while required work remains blocked or pending.

## Record template

Replace placeholders and omit study-only fields for unselected cycles. Keep an index link and current status in place of staged navigation; do not create empty Step 1–4 artifacts. Debug diagnostics remain a separate log when enabled. Render the cycle estimate as a standalone bold line near the top, and use the shared estimate presentation for any actual alternatives/work units. The compact outline below names required evidence; expand it with headings and dated entries as needed.

```text
Cycle: <stable identity>; Mode: one-shot; Record/index: <relative links>
Debug mode: enabled | disabled
Effort study: <selected study/cycle and host ledger link, if applicable>
Extended estimates: enabled | disabled <if enrolled>
**Cycle estimate: <whole-cycle value or unavailable reason, if enrolled>**
Status: <current lifecycle status>; next permitted action: <action>

Original request: <preserved request>
Authorization: <user instruction/evidence, date, scope and exclusions>
Outcome and work type: <application or documentation; allowed boundary>
Approach and risks: <proportionate plan, shared components, mitigations>
Concepts touched: <names/entry links, created/changed/used unchanged, proposed inventory updates; or none>
Verification and recovery plan: <normal entry, checks, failure/retry path>
Starting revisions and branch: <host/product where applicable>

Dated execution history:
- <decision/discovery/change; correction versus addition; verification>
- <new request, disposition/reason, approval and outcome/follow-up>
- <scope revision and actual authority; original scope retained>

Study history, when enrolled: <intake, entry, revisions, closeout>
Outcome: <delivered scope, limitations, incomplete work and next action>
Verification: <commands/results/omissions; environment and evidence limits>
Commit/merge/publication status: <distinct states and known revisions>
Attribution: <agent and UTC date; verified optional model/settings only>
```
