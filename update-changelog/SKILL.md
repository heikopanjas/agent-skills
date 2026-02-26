---
name: update-changelog
description: Record recent changes and decisions in the AGENTS.md file. Use when making project decisions, choosing technologies, establishing conventions, or completing significant changes that should be tracked in the project history.
compatibility: Requires an AGENTS.md file with a Recent Updates and Decisions section
---

# Update Changelog

After making significant project changes or decisions, record them in the "Recent Updates & Decisions" section at the bottom of AGENTS.md.

---

## When to Update

Add an entry whenever you:

- Make a technology or architecture decision
- Establish or change a coding convention
- Add, remove, or rename features or commands
- Perform significant refactoring
- Bump the project version
- Change build, test, or deployment procedures
- Make any decision that future contributors should know about

---

## Entry Format

Each entry starts with a heading containing the date, time, and an optional short label:

```
### YYYY-MM-DD HH:MM (label)

- Description of change or decision
- Reasoning if non-obvious
- Version bump if applicable
```

Rules:

- Use ISO date format: `YYYY-MM-DD`
- Always include the time in 24-hour format: `HH:MM`
- Add a parenthetical label when the change needs a short identifier (e.g. version number, feature name)
- Use bullet points for individual items within an entry
- Keep each bullet concise: what changed and why
- Mention version bumps inline: `Version bump: X.Y.Z to X.Y.Z (TYPE - reason)`
- Newest entries go first (reverse chronological order)

---

## Where to Write

The section must be at the **end** of AGENTS.md. Look for:

```markdown
## Recent Updates & Decisions
```

If the section does not exist, **create it** by appending the following to the bottom of AGENTS.md:

```markdown
---

## Recent Updates & Decisions
```

Then add the new entry below the heading.

Also update the `Last updated` timestamp near the top of AGENTS.md to today's date.

---

## Example

```markdown
## Recent Updates & Decisions

### 2026-02-25 14:30 (anyhow migration)

- Migrated error handling from custom Result type alias to anyhow crate
- lib.rs now re-exports pub use anyhow::Result
- Replaced all Err(format!(...).into()) with Err(anyhow!(...))
- Version bump: 9.0.2 to 9.0.3 (PATCH - internal refactor)

### 2026-02-24 09:15 (v9.0.0)

- MAJOR version bump: 8.0.0 to 9.0.0 (V1 removed, V3 template format)
- Removed V1 template engine and all V1 templates
- Introduced V3 template format with shared file groups and includes
```

---

## Do Not

- Do not remove or rewrite existing entries
- Do not move this section away from the bottom of the file
- Do not use this section for TODO items or planned work
- Do not duplicate the full commit message — summarize the decision and reasoning
