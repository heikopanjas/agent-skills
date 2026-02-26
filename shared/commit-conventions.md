# Shared: Commit Conventions

## Protocol

**NEVER commit automatically.** Always wait for explicit user confirmation before committing.

When asked to commit:

1. Stage the changes (see the specific skill for how)
2. Write a commit message following the guidelines below
3. Present the message to the user for confirmation
4. Commit only after confirmation

---

## Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Character Limits

- Subject line: 50 characters maximum (strict)
- Body lines: wrap at 72 characters
- Total message: under 500 characters
- Always add a blank line between subject and body

### Subject Line Rules

- Use conventional commit types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `build`, `ci`, `perf`
- Scope is optional but recommended: `feat(api):`, `fix(build):`
- Use imperative mood: "add feature" not "added feature"
- No period at end of subject line

### Body Rules

- Add blank line after subject before body
- Wrap each line at 72 characters
- Explain what and why, not how
- Use bullet points (`-`) for multiple items

### Special Character Safety

- Avoid nested quotes or complex quoting
- Avoid shell special characters: `$`, `` ` ``, `!`, `\`, `|`, `&`, `;`
- Use simple punctuation only
- No emoji or unicode characters

---

## Change Classification

Before writing a commit message, classify the change. This determines the conventional commit type, and whether a breaking change footer is needed.

| Change type | Example | Commit type | Breaking? |
|---|---|---|---|
| Typo in docs | Fix README wording | `docs` | No |
| Bug fix | Correct off-by-one error | `fix` | No |
| Refactor internals | Extract helper function | `refactor` | No |
| Performance tweak | Optimize hot loop | `perf` | No |
| Add new command | New `export` subcommand | `feat` | No |
| Add config option | New `--format` flag | `feat` | No |
| Rename public function | `process()` -> `run()` | `refactor` | Yes |
| Remove CLI flag | Drop `--legacy` option | `feat` or `fix` | Yes |
| Change output format | JSON keys renamed | `feat` or `fix` | Yes |

For breaking changes, add a `BREAKING CHANGE:` footer to the commit message:

```
refactor(api)!: rename process to run

BREAKING CHANGE: process() has been renamed to run()
```

---

## Best Practices

- **One concern per commit**: each commit should address one specific change
- **Break up large commits**: split into smaller, focused commits
- **Test before committing**: ensure code builds and works
- **Reference issues**: use `#123` format in footer if applicable

---

## Examples

Good:

```
feat(api): add KStringTrim function

- add trimming function to remove whitespace from
  both ends of string
- supports all encodings
```

Good (short):

```
fix(build): correct static library output name
```

Bad (too long subject):

```
feat(api): add a new comprehensive string trimming function that handles all edge cases
```

Bad (special characters):

```
fix: update `KString` with "nested 'quotes'" & $special chars!
```
