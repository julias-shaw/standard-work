# Definition of Ready

**Purpose** — a shared bar for when a story is defined well enough to start. It keeps
work from beginning while it's still vague, which is what leads to rework and unreliable
estimates.

**When it applies** — to a **story**, before it leaves the Backlog to be scheduled or
started (see [Status Tracking](status-tracking.md)). Tasks do not meet this bar
separately; they inherit their story's — see
[Stories and Tasks](stories-and-tasks.md).

**Roles** — the **developer** decides whether a story meets this bar. The **requester**
is the person who asked for the work. The **reviewer** is whoever performs any manual
review — **by default the requester**, but when creating the story the requester may
designate another person as the reviewer instead.

## Definition of ready

A story is ready when **all** of the following are true:

- [ ] **It is well enough defined that the developer understands it** and can
  **estimate it with 80% accuracy.** If the developer can't estimate it that
  confidently, it isn't ready. It needs more definition first.
- [ ] **Any story-specific acceptance criteria are captured** on the story, so it's
  clear what "correct" means for this particular work.
- [ ] **It states whether the story requires manual review** — review and approval by
  the reviewer — and, if so, **names the reviewer on the story.** Name them even when
  the reviewer is the requester, so it's never ambiguous who has to approve.

## How this relates to INVEST

The first two criteria above are the **E** and **T** of
[INVEST](stories-and-tasks.md#invest): a ready story must be **E**stimable and
**T**estable. Those two are all this bar *requires*.

A good story, though, meets all six — **I**ndependent, **N**egotiable, **V**aluable,
**E**stimable, **S**mall, **T**estable. Check a story against the full set while you're
writing it; check E and T before you start it. A story that is Estimable and Testable
but, say, not **S**mall is ready by this bar and still worth splitting.

## Related

- [Stories and Tasks](stories-and-tasks.md) — what a story is, the INVEST criteria for
  writing a good one, and how it breaks into tasks once it's ready.
- [Status Tracking](status-tracking.md) — stories in Backlog stay there until they meet
  this Definition of Ready.
- [Definition of Done](definition-of-done.md) — the matching bar for when the work is
  finished.
