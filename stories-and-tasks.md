# Stories and Tasks

**Purpose** — give the team one vocabulary for units of work, so that "story" and "task"
mean the same thing in every document, in Linear, and in conversation. Consistent names
make estimates comparable, status readable, and the rest of this library unambiguous.

**When it applies** — whenever work is written down, estimated, broken up, or reported
on.

**Roles** — the **requester** writes and owns the story (the *what*). The **developer**
breaks it into tasks and owns them (the *how*). The optional **reviewer** (by default the
requester) accepts the finished story. See the [Glossary](glossary.md) for each role in
brief, and [Definition of Ready](definition-of-ready.md) for the rule on naming a
reviewer.

## Story

A **story** is a unit of work that delivers something the requester values, described
from their point of view rather than in terms of how it will be built.

- **One story is one Linear issue.** If it isn't in Linear, it isn't tracked — see
  [Status Tracking](status-tracking.md).
- **The story is what everything else acts on.** It is the thing that gets estimated,
  prioritized, given acceptance criteria, carried through the statuses, and reviewed.
- **It is finished when it is usable**, not when one layer of it is built. A story cuts
  through whatever layers it needs to; "the database part" is not a story.
- **It meets the bars.** A story must meet the
  [Definition of Ready](definition-of-ready.md) before work starts and the
  [Definition of Done](definition-of-done.md) to be finished.

### INVEST

**INVEST** is a checklist for judging a story you've written — what makes a story a good
one. A story that fails one of these is usually the one that causes trouble later.

| Criterion | Means | Ask yourself |
| --- | --- | --- |
| **I**ndependent | It can be built and delivered without waiting on another story. | Could this ship on its own, in any order? |
| **N**egotiable | It describes what's needed, not a fixed contract for how to build it. | Is there still room to discuss the approach? |
| **V**aluable | Finishing it produces something the requester can perceive. | Can you say who is better off, and how? |
| **E**stimable | It's understood well enough to size. | Can the developer estimate it and be 80% confident in that estimate? |
| **S**mall | It fits in a short span of work. | Is it more than 2 ideal days? Then it *should* be split into more stories. |
| **T**estable | You can objectively tell whether it works. | Do its acceptance criteria say what "correct" means? |

**E** and **T** are the same ground the [Definition of Ready](definition-of-ready.md)
covers — a story that isn't Estimable or Testable isn't ready to start. A good story will
meet the other four criteria as well but that is not an absolute requirement.

## Task

A **task** is a step the developer identifies in order to deliver a story.

- **Written by and for the developer.** Technical language is expected — a task
  describes work, not customer value.
- **Every task belongs to exactly one story.** There are no orphan tasks. If a piece of
  work doesn't serve a story, it needs a story of its own.
- **Tasks carry no separate acceptance criteria.** The story's criteria are the bar.
- **Tasks are not separately reviewed or accepted.** The reviewer approves the story.
- **Only stories reach Done.** Finishing every task is part of how a story gets done;
  it is not a substitute for meeting the Definition of Done.

## Sizing in ideal days

Stories are sized in **ideal days**. An ideal day is a day of work with no interruptions,
no meetings, and everything you need already at hand — the story and nothing else.

Ideal days measure **size, not calendar time**. A two-ideal-day story normally spans more
than two days on the calendar, because real days contain everything else. That's the
point: sizing in ideal days lets you compare two stories to each other without having to
predict anyone's week.

## When to create tasks

The threshold is **2 ideal days**, measured against the estimate recorded at readiness
(see [Definition of Ready](definition-of-ready.md)). It works in two steps:

1. **A story of more than 2 ideal days *should* be split into more stories.** Being that
   big means it probably isn't **S**mall in [INVEST](#invest) terms. Splitting is the
   preferred answer.
2. **If it isn't split, it *must* be broken into tasks** — and no task is more than
   2 ideal days on its own. If a task still is, break it down further.

A story of **2 ideal days or less** needs no tasks at all. Write them if they help you
think, but nobody is asking for them.

Two ideal days is the point where "In Progress" stops being informative. Below it, the
status is a fair summary of where things stand; above it, only a task list tells anyone
how far along the work really is — so a big story that stays whole owes everyone a task
list in exchange.

## How tasks are tracked

Tasks are **checklist items on the story** — nothing more. They are not separate Linear
issues, and they carry no status of their own; the story's status covers all of them.

Keeping tasks inside the story keeps the tracking honest with little overhead: there is
one place to look for the state of the work, and the checklist shows how far along it
is.

## Definition of done

- [ ] Every tracked piece of work is a story, or a task belonging to a story.
- [ ] Each story is a single Linear issue with acceptance criteria and one status.
- [ ] Each story holds up against the E and T in INVEST.
- [ ] Any story of more than 2 ideal days has either been split into smaller stories or
  broken into tasks of at most 2 ideal days each.
- [ ] Tasks appear only as checklist items on their story.

## Related

- [Glossary](glossary.md) — short definitions of every term this library uses.
- [Definition of Ready](definition-of-ready.md) — the bar a story meets before work
  starts.
- [Definition of Done](definition-of-done.md) — the bar a story meets to be finished.
- [Status Tracking](status-tracking.md) — the statuses a story carries.
- [Version Control Usage](version-control-usage.md) — where a story's code lives in
  GitHub as it progresses.
