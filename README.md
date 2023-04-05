# Conventional Commits GitHub Action

A simple GitHub action that makes sure all commit messages are following the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/) specification.

![Screenshot](/docs/screenshot.png)

Note that, typically, you would make this check on a pre-commit hook (for example, using something like [Commitlint](https://commitlint.js.org/)), but those can easily be skipped, hence this GitHub action.

### Usage
Latest version: `v1.1.1`

```yml
name: Conventional Commits

on:
  pull_request:
    branches:
    - main
    - dev

jobs:
  check:
    name: Conventional Commits
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        name: Checkout code

      - uses: pallabpain/action-conventional-commits@v1.1.1
        name: Check commit hygiene
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
