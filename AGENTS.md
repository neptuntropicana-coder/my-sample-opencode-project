# AGENTS.md

Guidance for AI coding agents working in this repository.

## Project

`my-sample-opencode-project` is a minimal sample Git project. It exists to
demonstrate a clean, working repository setup rather than to contain application
code.

## Layout

| Path | Purpose |
|---|---|
| `README.md` | Project overview and usage |
| `.gitignore` | OS, editor, and temporary-file ignores |
| `.gitattributes` | Normalizes text files to LF; marks images binary |

There is no build system, dependency manifest, or test suite. Do not invent one
unless the task explicitly asks for it.

## Git workflow

- Default branch is `main`; it tracks `origin/main`. Work directly on `main`
  unless the task calls for a feature branch.
- Commit messages are short, imperative, and sentence-cased
  (e.g. `Add .gitignore`, `Update clone URL to the active GitHub account`).

### Remotes

| Remote | Target | Notes |
|---|---|---|
| `origin` | `git@github.com:neptuntropicana-coder/my-sample-opencode-project.git` | Primary; push and pull here |
| `local` | `~/Documents/Projekt domyślny/my-sample-opencode-project.git` | Bare mirror on disk; push to keep it in sync |

`git push` and `git pull` with no arguments use `origin`. After pushing to
`origin`, also push to `local` to keep the mirror current:

```bash
git push origin main
git push local main
```

## Environment notes

- Authentication is over SSH. `~/.ssh/config` pins the `github.com` host to
  `~/.ssh/id_github_neptuntropicana` with `IdentitiesOnly yes`, because another
  key on this machine belongs to a separate account.
- Do not alter `~/.ssh/config` or remove registered SSH keys without confirming
  first — other projects on this machine may depend on them.
- `gh` is authenticated as `neptuntropicana-coder`.
- Line endings are normalized to LF via `.gitattributes`; keep it that way.

## Agent skills

### Issue tracker

Local markdown under `.scratch/<feature-slug>/`. See `docs/agents/issue-tracker.md`.

### Triage labels

Default vocabulary: `needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`. See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: one `GLOSSARY.md` and `docs/adr/` at the repo root. See `docs/agents/domain.md`.
