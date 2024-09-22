<h1 align="center">
    poetry-build-action
</h1>

<p align="center">
    <img src="https://img.shields.io/github/release/devbruce/poetry-build-action.svg" />
</p>

This is a GitHub Action for setting up an environment based on [Poetry](https://python-poetry.org/) in the repository.  
It simplifies the process of building and caching the environment directly.

## Inputs

```yml
inputs:
  python-version:
    description: "Python Version"
    required: true
```

<br>

## Usages

```yml
name: "Usage: run pytest with poetry-build-action"
on: [push]

jobs:
  test:
    name: "Test"
    runs-on: ubuntu-24.04
    steps:
      #----------------------------------------------
      # Check out repo
      #----------------------------------------------
      - name: "Check out repository"
        uses: actions/checkout@v4
      #----------------------------------------------
      # Build & Cache environment with poetry
      #----------------------------------------------
      - name: "Build & Cache with Poetry"
        uses: devbruce/poetry-build-action@1.0.0
        with:
          python-version: "3.12"
      #----------------------------------------------
      # Run tests on poetry environment
      #----------------------------------------------
      - name: "Run tests"
        run: |
          poetry run pytest tests/
```

<br>

## References

- [Creating a composite action](https://docs.github.com/en/actions/sharing-automations/creating-actions/creating-a-composite-action)
- [Install Poetry Action(snok/install-poetry)](https://github.com/marketplace/actions/install-poetry-action)

<br>

## Authors

- Maintainer: @devbruce
