# Semver Release Action Action

A simple composite action designed to release a GitHub Action.

Automatically:
- Updates the Readme with `npalm/action-docs-action`. Include [these lines](https://github.com/npalm/action-docs#tldr) in your repo readme.
- Checks if your commit message contains `major|minor|patch`, assumes patch if none
- Does a release, incrementing the version appropriately

## Usage

```yaml
on:
  push:
    branches:
      - master
  repository_dispatch:
  workflow_dispatch:

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Do release
        uses: Makeshift/semver-release-action@master
        with:
          files: |
            action.yml
            *.js
            Readme.md
          readme: Readme.md

```

<!-- action-docs-inputs -->

<!-- action-docs-outputs -->
