# CLAUDE.md

Guidance for Claude Code (and any contributor) working in this repository.

## What this repository is

This repo documents **standard work** — in the lean-management sense — for an IT
organization that does **custom software development**. Each document captures the
current, agreed-upon best way to perform a recurring activity (intake, estimation,
code review, release, incident response, and so on), so the work is consistent,
teachable, and improvable.

It is primarily a **documentation repository** — prose and diagrams — but it may also
carry **executable standard work**. In the agentic-AI era, the best way to make a
practice repeatable is often to encode it as an **agent skill**, which can include
scripts. So expect some code here: skill definitions, helper scripts, and the like
that let an agent *perform* the standard work, not just describe it. When such code
exists, the general engineering rules apply to it (see [Scope note](#scope-note)).

The audience is any developer or team member reading it through the **GitHub web UI**,
so every document must render cleanly there without a local checkout or a build step.

This repo is the **foundation reused across different client engagements**, so keep it
free of any single client's specifics — no client names, team names, or individuals.
Use generic roles (e.g. "the developer") instead.

The **toolchain is standardized and may be named freely**: clients are standardized on
**GitHub** for version control and **Linear** for work tracking. Referring to these
tools by name is expected — they are the common baseline, not one client's incidental
choice.

## Repository layout

**All standard-work documents live at the repository root — a flat structure, on
purpose.** The point is to remove the overhead of "organizing" the repo: no debating
which folder a document belongs in, no deep paths, no reshuffling as topics grow. A
single flat namespace is good enough for Wikipedia, and it is good enough here. Order
and grouping are expressed in the `README.md` index, not in a directory tree.

The only carve-outs from the flat root are `images/` and `skills/` (below).

A flat layout also sidesteps a whole class of broken relative links: because documents
never move between folders, links between them don't break from relocation. (File
**renames** are the exception — those still break links, and must be fixed; see
[Renaming a document](#renaming-a-document).)

- **All standard-work documents live at the repository root.** No subdirectories for
  the documents themselves.
- **Images live in `/images`** at the root. Nothing else goes there.
- **`README.md` is the index and introduction.** It explains what standard work is,
  how to use this repo, and links to every document. It is the front door.
- **Agent skills live under `skills/`**, one self-contained directory per skill:
  `skills/<skill-name>/`, each with its own `SKILL.md` (plus any `references/`,
  scripts, or bundled templates the skill needs). Skills are packaged, portable units —
  they can be dropped into a client repo on their own — which is why they get a
  directory instead of sitting at the root. Link to a skill from the standard-work
  document it supports, and vice versa.

```
.
├── README.md                        # index + introduction (the front door)
├── CLAUDE.md                        # this file
├── definition-of-done.md            # a standard-work document
├── definition-of-ready.md           # …
├── stories-and-tasks.md             # …
├── version-control-usage.md         # …
├── status-tracking.md               # …
├── architecture-decision-records.md # …
├── images/                          # all images, referenced with relative paths
└── skills/                          # packaged agent skills, one directory each
    └── adr/
        ├── SKILL.md
        └── references/
            └── adr-template.md
```

## File naming

- **The filename is the kebab-case form of the document's single `# H1`, which is the
  first line of the document.** Lowercase the title, replace spaces with hyphens, drop
  punctuation, add `.md`. So a document whose first line is `# Status Tracking` is
  named `status-tracking.md`; `# Version Control Usage` → `version-control-usage.md`;
  `# Definition of Ready` → `definition-of-ready.md`. Title and
  filename stay in lockstep — renaming one means renaming the other.
- Names sort alphabetically in the root listing; the **intended reading order lives
  in the `README.md` index**, not in the filenames. Do not add numeric prefixes.
- Image files also use kebab-case, with a descriptive name: `release-flow.png`.
- **Files inside `skills/` follow agent-skill conventions instead** — e.g. the required
  `SKILL.md` filename and a `references/` subdirectory — not this kebab-case-of-H1 rule.

## Authoring conventions

- **GitHub Flavored Markdown (GFM) only.** Use the features GitHub renders natively —
  tables, task lists, fenced code blocks, blockquotes, footnotes, and
  ```mermaid``` diagrams. Do not rely on raw HTML or extensions GitHub won't render.
- **Relative links only** between documents: `[status tracking](status-tracking.md)`. Never
  link to a document by its full `https://github.com/...` URL — relative links keep
  working in forks, branches, and offline clones.
- **Images use relative paths** into `/images`: `![Release flow](images/release-flow.png)`.
  Always provide meaningful alt text.
- **One `# H1` per document**, matching the document's title, then `##`/`###` for
  sections. Don't skip heading levels.
- Write for scanability: short paragraphs, lists over walls of text, tables for
  anything with repeating structure. Prefer clear prose over jargon.
- Don't hard-wrap prose at a fixed column — GitHub reflows it. Let paragraphs be one
  line each, or wrap at sentence boundaries if you prefer readable diffs.

## Recommended document template

Standard work benefits from a predictable shape. Prefer this structure for each
document, but **deviate when a topic genuinely doesn't fit** — clarity wins over
uniformity.

The **first line of every document is its single `# H1`** — the title, from which the
filename is derived (see [File naming](#file-naming)). Nothing precedes it.

```markdown
# <Title of the standard work> — the single H1, and the first line of the file

**Purpose** — what this activity achieves and why it matters.

**When it applies** — the trigger or entry condition that starts this work.

**Roles** — who does what (use generic roles, not individuals).

## Steps

1. Ordered, concrete steps describing the current best-known way.

## Definition of done

- Checks or exit criteria that confirm the work was done correctly.

## Related

- Links to related standard-work documents.
```

## Keep the index in sync

The `README.md` index is only useful if it's complete. **In the same change that adds,
renames, or removes a document, update the `README.md` index** so it never drifts out
of sync with the files on disk.

## Renaming a document

Because the layout is flat, moving files never breaks links — but **renaming** one
does, since a rename changes both the `# H1` and the filename (they stay in lockstep).
When you rename `old-name.md` to `new-name.md`, find and fix every inbound link before
finishing:

1. **Find all references** to the old filename across the repo:

   ```sh
   grep -rn --include='*.md' 'old-name\.md' .
   ```

   This catches the `README.md` index entry and any `[text](old-name.md)` links in
   other documents. Also check for the bare stem if links might omit the extension.

2. **Update each match** to point at `new-name.md`, keeping the link text accurate to
   the new title.

3. **Verify none remain** — re-run the `grep` and confirm it returns nothing:

   ```sh
   grep -rn --include='*.md' 'old-name\.md' .
   ```

Only consider the rename complete once that final check is clean.

## Scope note

For the **prose documents**, the general rules are what matter: verify facts against
the actual files rather than assuming, keep the docs accurate, and keep the index in
sync.

For any **executable standard work** in the repo (agent skills, scripts), treat it as
real code: the code-oriented rules from global/user configuration **do apply** —
type-safe TypeScript for Node code, dependency-update quarantine, tests, and so on.
Encoding a practice as a runnable skill is encouraged, but a skill that ships broken
or untyped code is not standard work worth copying.
