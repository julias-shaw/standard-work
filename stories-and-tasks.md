# Stories and Tasks

**Purpose** — give the team one vocabulary for units of work, so that "story" and "task"
mean the same thing in every document, in Linear, and in conversation. Consistent names
make estimates comparable, status readable, and the rest of this library unambiguous.

**When it applies** — whenever work is written down, estimated, broken up, or reported
on.

**Roles** — the **requester** writes and owns the story (the *what*). The **developer**
breaks it into tasks and owns them (the *how*). The optional **reviewer** (by default the
requester) accepts the finished story. See
[Definition of Ready](definition-of-ready.md) for these roles in full.

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

| | Means | Ask yourself |
| --- | --- | --- |
| **I**ndependent | It can be built and delivered without waiting on another story. | Could this ship on its own, in any order? |
| **N**egotiable | It describes what's needed, not a fixed contract for how to build it. | Is there still room to discuss the approach? |
| **V**aluable | Finishing it produces something the requester can perceive. | Can you say who is better off, and how? |
| **E**stimable | It's understood well enough to size. | Can the developer estimate it with 80% accuracy? |
| **S**mall | It fits in a short span of work. | Is it more than a few days? Then split it into more stories. |
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

## When to create tasks

The rule of thumb is **two days**:

- A story of **2 days of work or less** doesn't need tasks. Write them if they help you
  think, but nobody is asking for them.
- A story of **more than 2 days of work** gets broken into tasks, and **no task is more
  than 2 days of work** on its own. If one still is, break it down further.

Two days is the point where "In Progress" stops being informative. Below it, the status
is a fair summary of where things stand; above it, only a task list tells anyone how far
along the work really is.

If a story can't be broken into tasks of two days or less, that's a signal about the
*story*, not the tasks — it probably isn't **S**mall enough, and should be split into
more stories.

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
- [ ] Any story of more than 2 days of work is broken into tasks of at most 2 days each.
- [ ] Tasks appear only as checklist items on their story.

## Related

- [Definition of Ready](definition-of-ready.md) — the bar a story meets before work
  starts.
- [Definition of Done](definition-of-done.md) — the bar a story meets to be finished.
- [Status Tracking](status-tracking.md) — the statuses a story carries.
- [Version Control Usage](version-control-usage.md) — where a story's code lives in
  GitHub as it progresses.
