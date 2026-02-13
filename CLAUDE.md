# CLAUDE.md

This file provides guidance to AI assistants working with the Claude-code repository.

## Repository Overview

**Claude-code** is a repository hosted at `pisarevaleksander/Claude-code`. It is currently in its initial state with no application code, build system, or dependencies configured yet.

## Current State

- The repository contains only a `README.md` with a basic project title and description.
- No programming language, framework, or tooling has been chosen yet.
- No source code, tests, or CI/CD pipelines exist.

## Repository Structure

```
Claude-code/
├── README.md          # Project description
└── CLAUDE.md          # This file — AI assistant guidance
```

## Git Workflow

- **Primary branch:** `main` (remote) / `master` (local)
- **Remote:** origin (GitHub)
- Feature branches should follow the naming convention: `claude/<description>-<id>`
- Write clear, descriptive commit messages summarizing the "why" behind changes
- Push with `git push -u origin <branch-name>`

## Development Guidelines

When adding code to this repository, follow these conventions:

### General Principles

- Keep solutions simple and focused — avoid over-engineering
- Do not add features, abstractions, or configuration beyond what is requested
- Prefer editing existing files over creating new ones
- Do not commit files containing secrets (`.env`, credentials, API keys)

### Code Quality

- Write clean, self-documenting code; add comments only where logic is non-obvious
- Follow the language and framework conventions established by the first meaningful commit
- Include tests for new functionality
- Validate inputs at system boundaries (user input, external APIs) but trust internal code

### File Organization

- Keep related files grouped logically by feature or module
- Place tests adjacent to source code or in a dedicated `tests/` directory (follow whichever convention is established first)
- Use consistent naming conventions across the project

## Updating This File

This CLAUDE.md should be updated as the project evolves:

- When a tech stack is chosen, document the languages, frameworks, and tools
- When a build system is configured, document build and run commands
- When tests are added, document how to run them
- When CI/CD is set up, document the pipeline
- When coding conventions are established, document the style guide and linting rules
