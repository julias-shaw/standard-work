# Architecture Decision Records

**Purpose** — record architecturally significant decisions, and the reasoning behind
them, at the time they are made. An Architecture Decision Record (ADR) preserves *why*
a choice was made — the context, the options considered, and the consequences — so
future readers don't have to reverse-engineer it or repeat the debate.

**When it applies** — when making an **architecturally significant decision**: one
that is costly to reverse, shapes the structure of the system, affects how components
fit together, or constrains future work. Small, easily reversible choices don't need
an ADR.

**Roles** — mirroring the fields in the template:

- **Decision-makers** — everyone who owns the decision and approves it.
- **Consulted** — those whose input is sought (two-way communication).
- **Informed** — those kept up to date on the outcome (one-way communication).

The person proposing the decision drives the ADR to a conclusion.

## Where ADRs live

ADRs belong with the code of the **project the decision concerns**, not in this
standard-work repository. This repo defines *how* we write ADRs; the ADRs themselves
live in their project's own repository so they sit next to the architecture they
describe.

## The ADR skill

This process is automated by the **`adr` agent skill** at
[`skills/adr/`](skills/adr/SKILL.md). It discovers where ADRs live in the target
project, creates a new ADR from the template, assigns the next number, and handles
status updates and supersession. Prefer the skill to do the work; the steps below
describe what it does — and what a hand-written ADR must still satisfy.

## Steps

1. **Start from the template.** Copy the ADR template —
   [`skills/adr/references/adr-template.md`](skills/adr/references/adr-template.md) — into a new
   file for the decision.
2. **Number and name it.** Assign the next sequential number, continuing the project's
   existing ADR sequence, and save it as `ADR-NNNN-kebab-case-title.md` (e.g.
   `ADR-0007-postgresql-for-backend.md`). The `ADR-NNNN` number is the identifier other
   ADRs reference when superseding; numbers are never reused.
3. **Fill in the record:** the short title, the context and problem statement, the
   considered options, and the chosen outcome with its consequences. Include decision
   drivers, confirmation, and pros/cons where they add clarity.
4. **Record the people:** list the decision-makers, and anyone consulted or informed.
5. **Set the status.** A new ADR starts as `proposed`; once the decision is made it
   becomes `accepted`, with the **Date** set to when it was last updated.
6. **Don't rewrite history.** An ADR is a record of a decision at a point in time. When
   a later decision changes it, mark the old one `deprecated`, or `superseded by
   ADR-NNNN` pointing at the ADR that replaces it — write a new ADR rather than editing
   the old one's outcome.

## Definition of done

- [ ] The ADR is created from [the ADR template](skills/adr/references/adr-template.md) and
  numbered `ADR-NNNN`.
- [ ] Its **Status** is accurate (`proposed`, `accepted`, `deprecated`, or `superseded
  by ADR-NNNN`) and its **Date** reflects the last update.
- [ ] Decision-makers are recorded, along with anyone consulted or informed.
- [ ] The context/problem, the considered options, and the chosen outcome with its
  consequences are all captured.

## Related

- [`adr` skill](skills/adr/SKILL.md) — the agent skill that automates creating,
  numbering, updating, and superseding ADRs.
- [ADR template](skills/adr/references/adr-template.md) — the template every ADR is created
  from, bundled with the skill.
