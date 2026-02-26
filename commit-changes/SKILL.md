---
name: commit-changes
description: Commit specific staged changes to a git repository using conventional commits format. Use when the user asks to commit, stage, or check in particular files or changes.
compatibility: Requires git
---

# Skill: commit-changes

Commit **specific changes** to a git repository. Only the relevant modified files are staged — not all changes in the working tree.

For commit message guidelines, protocol, and examples, read the shared conventions:
`shared/commit-conventions.md`

---

## Staging

Stage only the files relevant to the commit. Use `git add <file>...` rather than `git add -A`. If the user has not specified which files to include, inspect the working tree with `git status` and stage only the files that relate to the described change.
