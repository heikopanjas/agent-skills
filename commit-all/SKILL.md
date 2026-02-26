---
name: commit-all
description: Commit all current working tree changes to a git repository using conventional commits format. Use when the user asks to commit everything, commit all, or check in all changes.
compatibility: Requires git
---

# Skill: commit-all

Commit **all current changes** to a git repository. Every modified, added, and deleted file in the working tree is staged and included in a single commit.

For commit message guidelines, protocol, and examples, read the shared conventions:
`shared/commit-conventions.md`

---

## Staging

Stage all changes with `git add -A` before committing. No file filtering is applied.
