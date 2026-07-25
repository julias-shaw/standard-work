# Generic Standard Work

A living library of **standard work** for an IT organization that builds custom
software — the current, agreed-upon best way to do each recurring job, so the work
stays consistent, is easy to teach, and gets better over time.

New here? Skip down to [What is standard work?](#what-is-standard-work) for the intro.

## Index

- [Definition of Ready for Code](definition-of-ready-for-code.md) — the bar for when a
  piece of work is defined well enough to start.
- [Definition of Done for Code](definition-of-done-for-code.md) — the bar for when a
  code change is considered finished, and where it must live in GitHub.
- [Version Control Usage](version-control-usage.md) — keeping work on a branch, pushing
  to GitHub at least daily, and merging to the default branch when it reaches production.
- [Status Tracking](status-tracking.md) — tracking all work in Linear and what each
  status means.
- [Architecture Decision Records](architecture-decision-records.md) — when and how to
  record significant architecture decisions (uses the ADR template).

### Skills

Packaged agent skills that *perform* standard work, in [`skills/`](skills/):

- [`adr`](skills/adr/SKILL.md) — creates, numbers, updates, and supersedes Architecture
  Decision Records from the template.

<!--
As the library grows, you can group the index under sub-headings. For example:

### Planning
- [Definition of Ready for Code](definition-of-ready-for-code.md) — defined well enough to start.

### Delivery
- [Version Control Usage](version-control-usage.md) — where code lives at each stage.
- [Status Tracking](status-tracking.md) — tracking work in Linear.
-->

## What is standard work?

Borrowed from lean manufacturing, **standard work** is simply the best-known way to
perform a task, written down and agreed upon — until someone finds a better way and
updates it. It isn't bureaucracy and it isn't set in stone. It exists to:

- **Make good practice the default** — the right way is written down, not locked in
  one person's head.
- **Shorten onboarding** — new team members can read how we work instead of guessing.
- **Create a baseline for improvement** — you can only improve a process you've made
  explicit. Every document here is meant to be challenged and revised.

In the agentic-AI era, some standard work is best captured not just as a description
but as something an agent can *run* — an **agent skill**, sometimes with scripts.
Where that makes sense, you'll find runnable skills alongside the written guides.

## How this repo is organized

It's **flat on purpose**. Every document lives in the root of the repository — there
are no folders to navigate and no debate about where something "belongs." If a flat
namespace is good enough for Wikipedia, it's good enough for us, and it saves everyone
the overhead of organizing and reorganizing. The only exceptions are `images/` (all
images) and `skills/` (packaged agent skills, one directory each).

Order and grouping live in the [Index](#index) above, not in a directory tree. Every
document links to the related ones, so you can follow the trail from whichever one you
land on.

## How to use it

- **Reading?** Browse the [Index](#index) and open whatever's relevant. Each document
  tells you its purpose, when it applies, who's involved, and the steps.
- **Improving something?** Edit the document, and update this index in the same change
  if you add, rename, or remove a file. Standard work is meant to evolve — if you've
  found a better way, change it here so everyone benefits.
- **Adding a new practice?** Follow the shape of the existing documents (purpose →
  when it applies → roles → steps → definition of done → related) and add it to the
  index.
