# GitHub Action to install and setup `bk`

[![Build](https://github.com/buildkite/setup-bk/actions/workflows/use-action.yaml/badge.svg)](https://github.com/buildkite/setup-bk/actions/workflows/use-action.yaml)

Installs the latest version of [the Buildkite CLI][buildkite-cli] (`bk`) for use from GitHub Actions.

  [buildkite-cli]: https://github.com/buildkite/cli

## Example usage

```yaml
name: Push Package

on:
  push:
    branches: ["main"]

jobs:
  publish:
    name: Push Package
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - uses: buildkite/setup-bk
      - run: bk package push my-registry my-package.deb
```

## Thanks

Inspired by [setup-crane action][setup-crane-action] by @imjasonh.

  [setup-crane-action]: https://github.com/imjasonh/setup-crane
