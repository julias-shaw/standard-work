# Version Control Usage

**Purpose** — keep work visible, backed up, and easy to integrate by holding it in
version control from the very start rather than on an individual's computer. This is
what lets the team see status, review changes, and recover from a lost machine.

**When it applies** — to all code work: features, fixes, refactors, scripts, and agent
skills alike.

**Roles** — the **developer** keeps their work in version control as they go.

## Steps

1. **Do work in progress on a branch.** As soon as you start a change, create a branch
   for it. In-progress work lives on that branch, never only on your local machine.
2. **Push to GitHub at least daily.** Push your branch to GitHub no less than once a
   day while the work is active, so it is backed up and visible even before it's
   finished. More often is fine.
3. **Merge to the default branch when it's deployed to production.** When the change
   goes to production, it must be merged into the repository's default branch
   (whichever branch that repo designates as its default — it is not always named
   `main`). The default branch always reflects what is in production.

## Definition of done

- [ ] In-progress work is on a branch, pushed to GitHub, updated at least daily.
- [ ] Anything running in production is merged into the repository's default branch.

## Related

- [Definition of Done for Code](definition-of-done-for-code.md) — the overall bar for
  a finished change, which builds on these version-control practices.
