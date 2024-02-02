pre-commit-ast-grep
[![tag](https://img.shields.io/github/v/tag/boidolr/pre-commit-ast-grep?sort=semver)](https://github.com/boidolr/pre-commit-ast-grep/tags)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
================


Minimal git hooks to run [`ast-grep`](https://github.com/ast-grep/ast-grep) based on the [pre-commit](https://github.com/pre-commit/pre-commit) framework.

## Using pre-commit-ast-grep with pre-commit

Add this to your `.pre-commit-config.yaml`:
```
  - repo: https://github.com/boidolr/pre-commit-ast-grep
    rev: v0.2.0  # Use the ref you want to point at
    hooks:
      - id: ast-grep
```

### Automatically execute rewrites

```
  - repo: https://github.com/boidolr/pre-commit-ast-grep
    rev: v0.2.0  # Use the ref you want to point at
    hooks:
      - id: ast-grep
          args: ["--update-all"]
```

### Provide explicit configuration

```
  - repo: https://github.com/boidolr/pre-commit-ast-grep
    rev: v0.2.0  # Use the ref you want to point at
    hooks:
      - id: ast-grep
        args: ["--config", "/some/path/sgconfig.yaml"]
```

## How to write rules

See https://ast-grep.github.io/ for details on `ast-grep` and how to write linters and rewriters.