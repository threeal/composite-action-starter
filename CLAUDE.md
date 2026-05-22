# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

> **Template notice:** This file describes the template repository itself. If you've created a project from this template, replace this content with guidance specific to your project.

## Project Overview

This is a **GitHub template repository** for creating GitHub composite actions. The sample action (`action.yml`) implements a simple `mkdir` operation as a working example. Users create a new repo from this template and replace the sample with their own action logic.

## Architecture

The entire action is defined in a single file: `action.yml`. There is no build step, no source code, and no dependencies to install — composite actions execute shell commands directly.

- `action.yml` — action metadata, inputs, and bash step(s)
- `dprint.json` — formatter configuration (JSON, Markdown, YAML plugins)
- `lefthook.yaml` — pre-commit hook that runs `dprint fmt` on staged files and fails if any files were changed
- `.github/workflows/ci.yaml` — CI pipeline: formatting check and action tests across Ubuntu, macOS, and Windows

## Testing

Tests run as GitHub Actions workflows (no local test runner). To trigger CI:

- Push to `main` or open a pull request, or
- Trigger manually via the GitHub Actions UI (`workflow_dispatch`)

The CI workflow has two jobs:

- `check` — validates the pre-commit hook on Ubuntu
- `test` — runs the action on Ubuntu, macOS, and Windows

## Development Workflow

When adapting this template:

1. Edit `action.yml` to define new inputs and replace the sample bash step
2. Update `.github/workflows/ci.yaml` to test the new action's behavior
3. Update `README.md` to document the new action's inputs and usage
