# Status Tracking

**Purpose** — give everyone a single, accurate view of what work exists and where it
stands. Consistent statuses let anyone read the state of the work without asking.

**When it applies** — to all work.

**Roles** — the **developer** keeps their stories in Linear up to date and sets the
correct status. The one exception is **Done**: on a story that has a **reviewer**, the
reviewer sets it when they approve. See the [Glossary](glossary.md) for the roles.

## Track all work in Linear

All work is tracked in **Linear**. If a piece of work isn't captured as a Linear
story, it isn't tracked — create the story so its status is visible to the team.

## What carries a status

Only **stories** carry a status. **Tasks** are checklist items on their story and are
covered by the story's status — see [Stories and Tasks](stories-and-tasks.md).

## Statuses

Each story carries exactly one of the following statuses:

- **Backlog** — Work that is being planned but does not yet meet the
  [Definition of Ready](definition-of-ready.md), or has not been scheduled to
  begin work soon.
- **To Do** — This story is known, meets the
  [Definition of Ready](definition-of-ready.md), and is prioritized to begin soon but
  not yet started.
- **Blocked** — The story is actively blocked by something outside of your control. If
  the impediment is within your control, it is not Blocked — either keep working it
  (In Progress) or, if you've set it aside, mark it Paused. A story should not be
  paused unless a priority change has been approved. List any block(s) in the story
  details and who owns getting it unblocked.
- **Paused** — This story was begun but is not currently being worked on. This may
  happen due to a priority change or unplanned work. If the story is blocked by
  something outside of your control, use the Blocked status instead.
- **In Progress** — This story is actively being worked on and there are no known
  blockers stopping progress. If there are expected blockers coming up that are not
  currently blocking progress, the story is In Progress and the expected blockers
  should be listed in the story details.
- **In Review** — The developer believes the work is done and is waiting for **manual
  review** — review and approval by the story's reviewer. That is the requester (the
  person who asked for the work) unless they designated someone else as reviewer when
  they created the story. List who is reviewing it in the story details either way.
  If the reviewer **rejects** the work, the story leaves In Review: back to
  **In Progress** if the developer can start the requested changes right away, or
  **Paused** if they can't. Record what was asked for in the story details.
- **Done** — The story is completed and fully meets our
  [Definition of Done](definition-of-done.md). If the story has a reviewer, the
  **reviewer** sets this status when they approve; if it has none, the **developer**
  sets it. Over time we will refine our definition of done.
- **Archived** — Work that has been done and we no longer want to show on our
  Linear dashboard.
- **Cancelled** — Work that will not be done. It was decided the story is no longer
  wanted, so no further effort will be spent on it.
- **Duplicate** — This story duplicates another story and will not be worked on its own.
  Link to the story it duplicates in the details, and continue the work there.

## Related

- [Glossary](glossary.md) — short definitions of story, task, and the roles.
- [Stories and Tasks](stories-and-tasks.md) — what a story is, and how its tasks are
  tracked.
- [Definition of Done](definition-of-done.md) — the bar a story must meet before it
  can be marked Done.
