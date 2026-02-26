# agent-skills

A collection of reusable [Agent Skills](https://agentskills.io/) for AI coding agents.

## Skills

| Skill | Description |
|-------|-------------|
| [commit-changes](commit-changes/) | Commit specific staged changes using conventional commits format |
| [commit-all](commit-all/) | Commit all working tree changes using conventional commits format |
| [semantic-versioning](semantic-versioning/) | Determine and apply semantic version bumps after code changes |
| [update-changelog](update-changelog/) | Record recent changes and decisions in AGENTS.md |
| [c++-conventions](c++-conventions/) | C++ coding conventions and best practices for modern C++ development |
| [c-conventions](c-conventions/) | C coding conventions and best practices for C17 development |
| [swift-conventions](swift-conventions/) | Swift coding conventions and best practices for modern Swift development |
| [rust-conventions](rust-conventions/) | Rust coding conventions and best practices for idiomatic Rust development |

## Shared

The [shared/](shared/) directory contains conventions referenced by multiple skills:

- [commit-conventions.md](shared/commit-conventions.md) — commit message format, change classification, and best practices

## Installation

Copy the skill directories you want into your project's `.github/skills/`, `.claude/skills/`, or `.agents/skills/` folder. See the [Agent Skills specification](https://agentskills.io/specification) for details on where agents discover skills.

## Compatibility

Skills use only the portable frontmatter attributes (`name`, `description`, `compatibility`) and work across VS Code, Claude Code, and OpenAI Codex. See [AGENTS.md](AGENTS.md) for a full attribute compatibility table.

## License

[MIT](LICENSE)
