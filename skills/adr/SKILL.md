---
name: adr
description: >
  Create, update, and manage lightweight Architecture Decision Records (ADRs) using the MADR template.
  Use this skill whenever the user wants to: record an architecture decision, create an ADR, document
  a technical decision, update an ADR's status (propose, accept, deprecate, supersede), list existing
  ADRs, or supersede a previous decision. Also use when the user mentions "decision record",
  "architecture decision", "ADR", "tech decision log", or asks things like "why did we choose X" and
  no ADR exists yet. Even if the user just says "let's record this decision" or "we decided to use X",
  this skill applies.
---

# Architecture Decision Records

ADRs are short documents that capture a single architecturally significant decision -- one that affects
structure, non-functional characteristics, dependencies, interfaces, or construction techniques. They
serve as a decision log so future team members understand not just *what* was decided, but *why*.

The key insight from Michael Nygard: without ADRs, new team members face a bad choice between blindly
accepting past decisions (which may be outdated) or blindly reversing them (which may break things).
ADRs give them the context to make informed judgments.

## Discovering the ADR directory

Before creating or modifying any ADR, find where they live in this project:

1. Search for common ADR directory patterns: `docs/decisions/`, `doc/adr/`, `docs/adr/`, `adr/`, `decisions/`
2. Look for an existing template (`adr-template.md` or `TEMPLATE.md`) or files matching `ADR-*.md` / `0001-*.md` patterns
3. If found, confirm the directory with the user: "I found ADRs in `docs/decisions/`. Should I use that?"
4. If not found, ask the user where they'd like ADRs stored

If the directory contains a template (`adr-template.md` or `TEMPLATE.md`), use that. Otherwise, use
the bundled template at `references/adr-template.md`.

## Creating a new ADR

### 1. Determine the next number

Scan existing ADR files for the highest number. ADR filenames follow the pattern:

```
ADR-0001-phoenix-liveview-for-web-ui.md
ADR-0002-postrgresql-for-backend.md
```

The next ADR gets the next sequential number, zero-padded to 4 digits. Numbers are never reused --
if ADR-0003 was superseded, the next new ADR is still whatever follows the highest existing number.

### 2. Gather the decision details

Have a conversation with the user to understand:

- **What was decided?** Get a clear, specific decision statement
- **What problem does it solve?** The context and forces at play
- **What alternatives were considered?** At least the serious contenders
- **Why this option?** The deciding factors
- **What are the consequences?** Both positive and negative -- be honest about tradeoffs

Not every section in the template needs to be filled. The template includes optional sections marked
with HTML comments. Remove sections that don't add value for this particular decision -- a lean ADR
that captures the essentials is better than a bloated one with forced content.

### 3. Write the ADR

Fill in the template following these writing principles:

- **Title**: A short noun phrase that captures both the problem and the solution.
  Good: "Use Phoenix LiveView for real-time UI"
  Bad: "Frontend framework" or "Decision about how we handle UI"

- **Metadata table**: Place a markdown table immediately after the H1 title (no YAML frontmatter).
  This keeps metadata visible to anyone viewing the file, whether in GitHub, an editor, or a vault.
  The table has two columns -- Field and Value -- with rows for Status, Date, Decision-makers,
  Consulted, and Informed. Omit Consulted/Informed rows if they don't apply.

  ```markdown
  # Use Phoenix LiveView for real-time UI

  | Field | Value |
  |-------|-------|
  | **Status** | accepted |
  | **Date** | 2026-04-11 |
  | **Decision-makers** | Jane, Alex |
  ```

- **Status**: New ADRs start as `proposed` unless the user indicates the decision is already made,
  in which case use `accepted`

- **Date**: Use the current date in YYYY-MM-DD format

- **Context section**: Describe the forces at play -- technical, political, social, project-specific.
  Use value-neutral language. This section answers "what situation are we in?"

- **Decision section**: State the decision in active voice: "We will use...", "We will not...",
  "We will migrate from X to Y...". Be specific enough that someone could act on it.

- **Consequences**: List all significant outcomes -- good, bad, and neutral. Being upfront about
  downsides builds trust in the document and helps future readers weigh whether the tradeoffs
  still make sense.

Write it as a conversation with a future developer. Full sentences, not just bullet fragments.
Keep it to 1-2 pages -- long enough to capture the reasoning, short enough to actually get read.

### 4. Save the file

Save as `ADR-NNNN-kebab-case-title.md` in the ADR directory. The kebab-case title should be
derived from the ADR title -- readable when scanning a directory listing.

## Updating ADR status

ADRs move through these statuses:

| Transition | When | What to do |
|---|---|---|
| `proposed` -> `accepted` | Team agrees to adopt the decision | Update the Status and Date rows in the metadata table |
| `accepted` -> `deprecated` | Decision is no longer relevant (e.g., the feature was removed) | Update Status and Date in the metadata table, add a note in "More Information" explaining why |
| `accepted` -> `superseded by ADR-NNNN` | A new decision replaces this one | See "Superseding an ADR" below |

When updating status, always update the Date row in the metadata table to the current date.

Never delete an ADR. The historical record has value -- it shows what was tried, what the thinking
was at the time, and why things changed.

## Superseding an ADR

When a new decision replaces an old one:

1. **Create the new ADR** (following the normal creation flow above). In its Context section,
   reference the old ADR and explain what changed -- new information, shifted requirements,
   lessons learned -- that motivated revisiting the decision.

2. **Update the old ADR's status** to `superseded by ADR-NNNN` where NNNN is the new ADR's number.
   Add a note in the old ADR's "More Information" section pointing to the new ADR and briefly
   explaining the reason for supersession.

This creates a clear chain: anyone reading the old ADR immediately knows it's been replaced and
where to find the current thinking.

## Listing ADRs

When the user asks to see existing ADRs, scan the ADR directory and present a table:

```
| # | Title | Status | Date |
|---|-------|--------|------|
| ADR-0001 | Use Phoenix LiveView for real-time UI | accepted | 2026-04-11 |
| ADR-0002 | PostgreSQL for data storage | accepted | 2026-04-11 |
```

Parse the metadata table to extract status and date. The title is the H1 heading.
