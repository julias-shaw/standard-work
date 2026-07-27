# Definition of Ready for Code

**Purpose** — a shared bar for when a piece of work is defined well enough to start.
It keeps work from beginning while it's still vague, which is what leads to rework and
unreliable estimates.

**When it applies** — before a work item leaves the Backlog to be scheduled or started
(see [Status Tracking](status-tracking.md)).

**Roles** — the **developer** decides whether an item meets this bar. The **requester**
is the person who asked for the work. The **reviewer** is whoever performs any manual
review — **by default the requester**, but when creating the item the requester may
designate another person as the reviewer instead.

## Definition of ready

Work is ready when **all** of the following are true:

- [ ] **It is well enough defined that the developer understands it** and can
  **estimate it with 80% accuracy.** If the developer can't estimate it that
  confidently, it isn't ready. It needs more definition first.
- [ ] **Any work-specific acceptance criteria are captured** on the item, so it's clear
  what "correct" means for this particular work.
- [ ] **It states whether the work requires manual review** — review and approval by
  the reviewer — and, if so, **names the reviewer on the item.** Name them even when
  the reviewer is the requester, so it's never ambiguous who has to approve.

## Related

- [Status Tracking](status-tracking.md) — items in Backlog stay there until they meet
  this Definition of Ready.
- [Definition of Done for Code](definition-of-done-for-code.md) — the matching bar for
  when the work is finished.
