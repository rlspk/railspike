# Welcome to Railspike

Agent instructions: follow this file after inspection and successful installation. If inspection raised concerns or an installation check failed, explain the issue and stop instead. Give a brief, conversational welcome using the guidance below; do not reprint this file. Announce the first-task default, then end the welcome turn with only the project-guidance question below. Ask for a task after the user replies to it.

## Introduce the workflow

- Confirm the installation type, location, and reviewed source revision; summarize the project changes and their commit status. Report inspection findings and limitations if not already covered; do not describe inspection as a safety guarantee.
- Explain: Railspike helps you assess approaches, define the feature, plan the work, and implement it in stages. Plans live in the project's `docs/plans/` so the user can read and revise them. Step 1 is optional when the approach is obvious.
- Explain the staged approval points: review each planning artifact, ask for changes, and reply `Approved Step 1`, `Approved Step 2`, or `Approved Step 3` when ready. Implementation begins after Step 3 approval, on a feature branch with staged verification and commits.
- Explain: explicitly authorized bounded one-shot work uses one evolving development record with the same substantive evidence and no intermediate step approvals. A question or plan reference does not authorize execution. Ordinary small tasks can still proceed outside Railspike.
- Say: “I’ll use Railspike for your next substantial task unless you say otherwise. Small, straightforward changes can proceed directly.” This begins planning when a task arrives; it does not approve implementation.
- Show one copyable explicit-use example for later sessions, replacing the path below with the actual installed path to Railspike's `RAILSPIKE.md`:

```text
I want to [describe my change]. Write Step 1 using docs/railspike/RAILSPIKE.md.
```

## Offer optional project guidance

Offer to add the following guidance to the host project's `AGENTS.md`. Substitute the actual installed path and show the proposed text before requesting consent. Explain that this makes the default persist across sessions; the current welcome session already uses the first-task default. This is an offer, not authorization to edit the file. End the welcome turn with one yes/no question as its final line, such as “Add this to AGENTS.md? (yes/no)”. Do not ask for a task or add anything after it in the same turn, so the question is answered rather than overlooked.

```markdown
## Railspike

Use Railspike by default when a task would benefit from comparing approaches, staged planning, or work across sessions, unless the user opts out. Read `docs/railspike/RAILSPIKE.md` and begin the appropriate planning step; wait for each required `Approved Step N` before advancing. Small, straightforward changes can proceed directly outside Railspike. For explicitly requested, bounded Railspike one-shot execution, use its one-shot workflow and record actual authorization before implementation; questions and plan references grant no new authority. Honor a decline for the same task without repeated offers. This guidance does not approve implementation.
```

## Handle the guidance reply

- **Yes:** inspect the host project's existing `AGENTS.md` and preserve its unrelated guidance. Propose an update to an existing Railspike entry instead of adding a duplicate; if the file is absent, create it only with consent. Stop and clarify conflicts instead of silently replacing project rules. Report any edit for the project's normal review/commit process.
- **No:** leave the file unchanged and do not offer again.
- **Anything else**, including a task, “later”, or a question: leave the file unchanged. Say in one line that the guidance was not added and that the user can ask for it at any time, and do not ask again in this session. Then respond to what they said; a task proceeds without waiting.

Always state the result in one line: `AGENTS.md: added`, `AGENTS.md: declined`, or `AGENTS.md: not answered`. Declining persistent guidance alone does not opt out of the current first-task default, while an explicit request not to use Railspike for the task takes precedence.

## Invite the first task

After handling the guidance reply, ask what the user wants to work on, unless the reply already gave a task. If a task was supplied with the installation request, start it after the guidance reply; do not ask them to repeat it. Once a suitable task arrives, read the installed `RAILSPIKE.md`. For explicitly authorized bounded one-shot execution, follow its one-shot workflow. Otherwise start Step 1 when approaches need comparison, or Step 2 when the approach is clear. Do not ask for a second opt-in merely because the user answered with only a task. For an existing workflow, restore its execution mode, actual authority and current state rather than inventing approvals or restarting it.

For example, “Help me deploy this extension to the Chrome extensions store” is a substantial task: begin planning its release work and save the artifact for review. Do not jump from that request into implementation. A small, standalone correction can proceed directly; a follow-up correction within an active Railspike workflow still respects that workflow's approved scope and gates. If the user opts out, honor that choice without repeated suggestions.

Stop at the first applicable planning approval gate. Accepting optional project guidance alone supplies neither a task nor step approval. Without persistent guidance, describe this as the current welcome session's default; in a later session the user can explicitly invoke Railspike with the example above.
