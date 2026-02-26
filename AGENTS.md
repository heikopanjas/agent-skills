# Agent Skills Repository

## SKILL.md Frontmatter Attribute Compatibility

| Attribute | Standard | Claude Code | VS Code | Codex |
|-----------|:--------:|:-----------:|:-------:|:-----:|
| `name` | Yes | Yes (optional) | Yes (required) | Yes (required) |
| `description` | Yes | Recommended | Yes (required) | Yes (required) |
| `compatibility` | Yes | Yes | Yes | — |
| `license` | Yes | Yes | Yes | — |
| `metadata` | Yes | Yes | Yes | — |
| `argument-hint` | — | Yes | Yes | — |
| `user-invocable` / `user-invokable` | — | Yes (`user-invocable`) | Yes (`user-invokable`) | — |
| `disable-model-invocation` | — | Yes | Yes | — |
| `allowed-tools` | Yes | Yes | — | — |
| `model` | — | Yes | — | — |
| `context` | — | Yes | — | — |
| `agent` | — | Yes | — | — |
| `hooks` | — | Yes | — | — |

Codex uses a separate `agents/openai.yaml` file for extended configuration:

| `openai.yaml` field | Equivalent to |
|---|---|
| `policy.allow_implicit_invocation: false` | `disable-model-invocation: true` |
| `dependencies.tools` | `allowed-tools` (declares MCP dependencies) |
| `interface.display_name` | `name` (user-facing) |
| `interface.short_description` | UI description |
| `interface.icon_small` / `icon_large` | No equivalent elsewhere |
| `interface.brand_color` | No equivalent elsewhere |
| `interface.default_prompt` | No equivalent elsewhere |

### Sources

- [Agent Skills Specification](https://agentskills.io/specification)
- [Claude Code Skills](https://code.claude.com/docs/en/skills)
- [VS Code Agent Skills](https://code.visualstudio.com/docs/copilot/customization/agent-skills)
- [OpenAI Codex Skills](https://developers.openai.com/codex/skills)
