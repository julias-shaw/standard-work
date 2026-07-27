# Definition of Done

**Purpose** — a shared, unambiguous bar for when a story is "done." It keeps work from
lingering in a half-finished state and, where a story involves code, makes the state of
that code visible to the whole team through GitHub.

**When it applies** — to every **story**, no matter how small (see
[Stories and Tasks](stories-and-tasks.md)). Most criteria apply to every story; the
version-control criteria apply only to stories that involve code.

**Roles** — the **developer** is responsible for getting the story to done. Where the
story calls for manual review, the **reviewer** named at readiness reviews and approves
it, and sets the story to Done; on a story with no reviewer, the developer does. See the
[Glossary](glossary.md) for the roles.

## Definition of done

**Every** story is done when **all** of the following are true:

- [ ] **Any story-specific acceptance criteria are met**, if the story has them. These
  are the criteria captured at readiness (see
  [Definition of Ready](definition-of-ready.md)); the work isn't done until they are all
  satisfied.
- [ ] **Any manual review required at readiness has been completed and approved.** If the
  [Definition of Ready](definition-of-ready.md) specified a manual review, the reviewer
  named there must have reviewed the work and approved it.

### Additionally, for stories that involve code

A story that produces or changes code — features, fixes, refactors, scripts, and agent
skills alike — is not done until this is also true:

- [ ] **It is in GitHub, version-controlled per
  [Version Control Usage](version-control-usage.md).** Work that lives only on a local
  machine is not done — it isn't visible, backed up, or reviewable. In short:
  in-progress work is on a branch; anything running in production is merged into the
  repository's default branch. See that document for the full practice.

A story with no code (a decision, a piece of research, a conversation that had to
happen) is done on the criteria above alone. Nothing here asks for a branch that would
have nothing on it.

## Related

- [Glossary](glossary.md) — short definitions of story, task, and the roles.
- [Definition of Ready](definition-of-ready.md) — where a story's acceptance criteria
  are captured before work starts.
- [Stories and Tasks](stories-and-tasks.md) — why only stories reach Done, and tasks
  don't.
- [Version Control Usage](version-control-usage.md) — where code must live in GitHub at
  each stage, for the stories that involve code.
- [Status Tracking](status-tracking.md) — a story can only reach the **Done** status
  once it meets this Definition of Done.
