---
name: semantic-versioning
description: Determine whether a version bump is required after code changes and apply semantic versioning (SemVer). Use when making code changes, fixing bugs, adding features, or introducing breaking changes to a project that uses SemVer.
compatibility: Requires a project with a version field (e.g. Cargo.toml, package.json)
---

# Semantic Versioning

After making code changes, determine whether a version bump is required and which component to increment.

## Version Format: MAJOR.MINOR.PATCH

### PATCH (X.Y.Z -> X.Y.Z+1)

Increment for changes that do not affect the public API:

- Bug fixes and minor corrections
- Performance improvements
- Documentation updates
- Internal refactoring

### MINOR (X.Y.Z -> X.Y+1.0)

Increment for backward-compatible additions:

- New features
- New CLI commands or options
- New public API surface

Reset PATCH to 0 when incrementing MINOR.

### MAJOR (X.Y.Z -> X+1.0.0)

Increment for breaking changes:

- Removal of features or commands
- Incompatible API changes
- Changes that require user action or code updates

Reset MINOR and PATCH to 0 when incrementing MAJOR.

---

## Process

1. Review the changes made
2. Classify the change using the guide in `shared/commit-conventions.md`
3. Find the current version in the project manifest (e.g. `Cargo.toml`, `package.json`)
4. Map the classification to a version bump (see below)
5. Increment the appropriate version component
6. Include the version bump in the same commit as the code change
7. Mention the version bump in the commit message footer if significant

**Do not create a separate commit for the version bump.** It belongs with the change that caused it.

---

## Classification to Version Bump

| Classification | Bump |
|---|---|
| Non-breaking fix, refactor, docs, perf | PATCH |
| Non-breaking feature | MINOR |
| Breaking change | MAJOR |
