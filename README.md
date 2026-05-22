# Composite Action Starter

A minimal template for building a [composite GitHub Action](https://docs.github.com/en/actions/sharing-automations/creating-actions/creating-a-composite-action).

## Getting Started

Create a new repository from this template on GitHub using [this link](https://github.com/new?template_name=composite-action-starter&template_owner=threeal).

Or clone it locally and point it at your own remote.

## Setup

Install [Lefthook](https://lefthook.dev/), then register the pre-commit hooks:

```sh
lefthook install
```

## Customizing the Action

### `action.yml`

Update the action's name, description, branding, inputs/outputs, and steps to match what your action does.

### `LICENSE`

The template ships with the [Unlicense](https://unlicense.org/) (public domain). Replace it with the license you want, or leave it as-is.

## Development Workflow

Edit `action.yml` directly. When you're ready, just commit — the pre-commit hook will automatically format all files using [dprint](https://dprint.dev/).

If the hook reports errors, fix them and commit again.

## CI

`.github/workflows/ci.yaml` runs two jobs on every push and pull request:

- **check** — validates the pre-commit hook on Ubuntu
- **test** — runs the action on Ubuntu, macOS, and Windows

Update the `test` job to exercise your action's actual inputs and verify its outputs.

## Releasing

Tag a release on GitHub:

```sh
git tag v1.0.0
git push origin v1.0.0
```

Then create a GitHub Release from that tag. To make the action discoverable, [publish it to the GitHub Marketplace](https://docs.github.com/en/actions/sharing-automations/creating-actions/publishing-actions-in-github-marketplace) from the release page.
