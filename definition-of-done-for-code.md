# Definition of Done for Code

**Purpose** — a shared, unambiguous bar for when a piece of code is "done." It keeps
work from lingering in a half-finished state on someone's computer and makes the status
of any change visible to the whole team through GitHub.

**When it applies** — to every code change, no matter how small: features, fixes,
refactors, scripts, and agent skills alike.

**Roles** — the **developer** is responsible for getting the change to done.

## Definition of done

Code is done when **all** of the following are true:

- [ ] **It is checked into GitHub.** Work that lives only on a local machine is not
  done — it isn't visible, backed up, or reviewable.
- [ ] **It is version-controlled per [Version Control Usage](version-control-usage.md).**
  In short: in-progress work is on a branch; anything running in production is merged
  into the repository's default branch. See that document for the full practice.
- [ ] **Any work-specific acceptance criteria are met**, if the item has them. These are
  the criteria captured at readiness (see
  [Definition of Ready for Code](definition-of-ready-for-code.md)); the work isn't done
  until they are all satisfied.
- [ ] **Any manual review required at readiness has been completed and approved.** If the
  [Definition of Ready for Code](definition-of-ready-for-code.md) specified a manual
  review — review and approval by the requester — that review must be done and the work
  approved.

## Related

- [Definition of Ready for Code](definition-of-ready-for-code.md) — where a work item's
  acceptance criteria are captured before work starts.
- [Version Control Usage](version-control-usage.md) — where code must live in GitHub at
  each stage.
- [Status Tracking](status-tracking.md) — an item can only reach the **Done** status
  once it meets this Definition of Done.
