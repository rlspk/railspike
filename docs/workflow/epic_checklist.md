# Epic checklists

An epic is one outcome delivered in several cycles, some one-shot and some staged. Its checklist is a coordination record in the host's `docs/plans/{epic}_checklist.md`. It approves nothing. Each item stays its own cycle, with its own authorization, branch, plans and commits under [RAILSPIKE.md](../../RAILSPIKE.md).

## When to make one

Suggest an epic when a Step 1 estimate goes above 1.0 or a plan exceeds eight stages. Create one only when the user asks. Writing the checklist is a documentation-only [one-shot](one_shot.md): its own record, branch and commits. Updating it later belongs to whichever cycle changed its state.

## Rules

- **Resume here comes first.** It names the next item, its step, what it waits on, its branch and the last session's date. Update it at the end of every session. A [handoff prompt](../../RAILSPIKE.md#handoff-prompts) for an epic points to the checklist first.
- **Mode is a lean.** "(one-shot)" or "(staged)" on an item is a plan, not authorization. Settle the mode and get authorization when the item starts. One-shot items may still move to staged under the one-shot transition rules.
- **Stable IDs.** Give each item a number and a cycle name. Never renumber. A new item takes the next free number, even when it runs between earlier ones.
- **Status in layers.** Record built, PR, merged, deployed, checked by the named user, and accepted, each on its own. A merged item is not yet an accepted one.
- **Follow-ups nest.** A follow-up cycle that comes from an item's review goes under that item, with its own name, record and status.
- **Links both ways.** Each item links its plans or record. Each cycle's first artifact links back to the checklist.
- **Approver.** One line says who approves steps. Record any delegation, its scope and when it ends.
- **MVP line.** Mark which items make the first usable release. Items past the line are candidates, not commitments.
- **Keep history.** Strike through a cut item and say why and when. Mark a superseded item with a link to what replaced it. Record a replan with the user's words. Never delete an item.
- **Estimates.** Each item may carry a whole-cycle estimate. Never sum them. For the effort study, each epic cycle is its own outcome, linked to the epic; the split rules still apply inside a cycle.
- **Re-check before planning.** The reuse inventory is a first read. Each item checks its own part again before planning.

Only Resume here and Items are required. Add the other sections when they have content.

## Template

```md
# {Epic} checklist

Coordination record for {outcome}. It is not a Railspike artifact and approves no implementation. Each item is its own Railspike cycle. Requested by {user} on {date}. Approver: {user}; {delegation, if any}.

## Resume here

Next: item {N} `{cycle}` ({mode lean}), {step}; waiting on {what}. Branch `{branch}` from `{base}`. Last session: {date}.

## Reuse inventory

Read at `{commit}`. Each item re-checks its own part before planning.

- {path}: {what it offers}

## Items

- [ ] **1. `{cycle}`** ({mode lean}; estimate {value}) — {what it delivers}. [Plans or record]({link})
  - Status: built · PR {link} · merged {date} · deployed {date} · checked {who, date} · accepted {date}
- MVP line: items 1–{N}.

## Decisions so far

- {decision} ({date})

## Open questions

1. {question} (item {N})

## Later, not planned

- {candidate}
```
