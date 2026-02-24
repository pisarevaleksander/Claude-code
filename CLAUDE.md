# CLAUDE.md

This file provides guidance for AI assistants (Claude Code and similar tools) working in this repository.

---

## Project Overview

**Repository:** Claude-code
**Owner:** pisarevaleksander
**Status:** Early initialization — no source code exists yet. This file establishes conventions and workflows to follow as the project grows.

The README currently contains only a placeholder. Update it with a meaningful description once the project purpose is defined.

---

## Repository Structure

```
Claude-code/
└── README.md       # Project description (placeholder)
└── CLAUDE.md       # This file — AI assistant guidance
```

No source code, dependencies, build system, tests, or configuration files exist yet. When adding them, follow the conventions in this document.

---

## Git Conventions

### Branches

- `master` — stable, protected branch. Do not push directly without a review.
- `claude/<description>-<session-id>` — branches used by AI assistants for task-scoped work.
- Feature branches should follow: `<username>/<short-description>` (e.g., `pisarevaleksander/add-auth`).

### Commits

- Use clear, imperative commit messages: `Add user authentication`, `Fix null pointer in parser`.
- Keep commits focused — one logical change per commit.
- This repository uses **SSH commit signing**. Commits must be signed; do not use `--no-gpg-sign`.

### Push Workflow

```bash
# Always set upstream on first push
git push -u origin <branch-name>

# Branch names for AI sessions must match exactly:
# claude/<description>-<session-id>
# Mismatched names will fail with HTTP 403.
```

If a push fails due to a network error, retry with exponential backoff: wait 2s, 4s, 8s, 16s between attempts.

---

## Development Workflow

Since the project has no code yet, follow this workflow when adding the first code:

1. **Define the project type** — choose language, framework, and purpose. Update `README.md`.
2. **Initialize dependency management** — `package.json`, `requirements.txt`, `Cargo.toml`, etc.
3. **Add configuration** — linter, formatter, and editor configs before writing substantive code.
4. **Set up tests** — add a test framework and at least one smoke test before shipping any feature.
5. **Add CI/CD** — create `.github/workflows/` (or equivalent) to run tests and linting on every push.
6. **Work in feature branches** — never commit directly to `master`.

---

## Code Style (To Be Defined)

No language or framework has been selected yet. Once decided, add the following to this section:

- Language version (e.g., Python 3.12, Node 22, Rust 1.78)
- Formatter and configuration (e.g., Prettier, Black, rustfmt)
- Linter and rules (e.g., ESLint, Ruff, Clippy)
- Naming conventions (variables, functions, files, modules)
- Import ordering rules
- Maximum line length

---

## Testing (To Be Defined)

No test framework has been configured yet. Once chosen, document:

- Framework name and version
- How to run the full test suite
- How to run a single test
- Where test files live relative to source files
- Coverage requirements (if any)

---

## Environment Setup (To Be Defined)

No environment variables or secrets are required yet. When added:

- Document all variables in `.env.example` with descriptions but no real values.
- Never commit `.env` or files containing secrets.
- Add `.env` to `.gitignore` immediately when creating one.

---

## Instructions for AI Assistants

### Before Making Changes

- Read the files you intend to modify — never edit code you haven't read.
- Check `git status` and `git log` to understand the current state of the branch.
- Use `git diff` to verify no unintended changes are staged.

### Making Changes

- Prefer editing existing files over creating new ones.
- Do not add comments, docstrings, or type annotations to code you did not change.
- Do not refactor, rename, or "clean up" code unless explicitly asked.
- Do not add error handling for scenarios that cannot happen.
- Keep solutions minimal — the right amount of complexity is the minimum needed.
- Remove dead code completely rather than commenting it out.

### Git Operations

- Work only on the branch specified in the task — never push to `master` without explicit instruction.
- Stage specific files by name rather than `git add -A` or `git add .` to avoid accidentally including secrets or binaries.
- Pass commit messages via heredoc to preserve formatting:

```bash
git commit -m "$(cat <<'EOF'
Add feature X

Detailed explanation if needed.
EOF
)"
```

- After committing, run `git status` to confirm the working tree is clean.
- Push with `-u origin <branch-name>` and verify the push succeeded.

### Security

- Never commit secrets, API keys, tokens, or passwords.
- Do not introduce: SQL injection, XSS, command injection, path traversal, or other OWASP Top 10 vulnerabilities.
- Validate all input at system boundaries (user input, external APIs); trust internal code.

### What Not to Do

- Do not create files unless absolutely necessary for the task.
- Do not generate speculative code for hypothetical future requirements.
- Do not use time estimates (e.g., "this will take a few minutes").
- Do not push to a branch other than the one specified in the task.
- Do not amend previous commits unless explicitly instructed — always create new commits.

---

## Useful Commands

```bash
# Show working tree status
git status

# Show recent commits
git log --oneline -10

# Show staged and unstaged changes
git diff HEAD

# Create and switch to a new branch
git checkout -b <branch-name>

# Push current branch and set upstream
git push -u origin <branch-name>
```

---

*Last updated: 2026-02-24*
