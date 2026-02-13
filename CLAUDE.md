# CLAUDE.md

This file provides guidance for AI assistants working with this repository.

## Project Overview

**Claude-code** is a repository owned by `pisarevaleksander`. It is currently in its initial state with no application code yet — only a README.md exists.

## Repository Structure

```
Claude-code/
├── README.md          # Project description
└── CLAUDE.md          # This file — AI assistant guidance
```

## Branch Strategy

- **main** — the primary branch on the remote
- **master** — local default branch from initial commit
- Feature branches follow the pattern `claude/<description>-<id>`

## Git Conventions

- Remote is configured as `origin`
- Push with: `git push -u origin <branch-name>`
- Feature branches should be created off the latest `main`

## Development Guidelines

Since this is a new repository, the following guidelines should be applied as code is added:

### General Principles

- Keep changes focused and minimal — avoid over-engineering
- Do not introduce unnecessary abstractions for one-time operations
- Prefer editing existing files over creating new ones
- Do not add comments, docstrings, or type annotations to unchanged code

### Code Quality

- Do not introduce security vulnerabilities (command injection, XSS, SQL injection, etc.)
- Validate inputs at system boundaries (user input, external APIs) but trust internal code
- Avoid backwards-compatibility shims — if something is unused, remove it

### Commits

- Use clear, descriptive commit messages
- Focus commit messages on the "why" rather than the "what"
- Keep commits atomic — one logical change per commit

## Current State

This repository is in its initial bootstrapping phase. As the project evolves, this file should be updated to reflect:

- The chosen language/framework and build system
- Source code directory structure and module organization
- How to install dependencies, build, and run the project
- Testing framework, test commands, and testing conventions
- Linting and formatting tools and their configuration
- CI/CD pipeline details
- Key architectural decisions and patterns used
- Environment variables and configuration requirements
