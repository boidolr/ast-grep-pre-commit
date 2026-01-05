ast-grep-pre-commit
[![tag](https://img.shields.io/github/v/tag/boidolr/ast-grep-pre-commit?sort=semver)](https://github.com/boidolr/ast-grep-pre-commit/tags)
[![Build](https://github.com/boidolr/ast-grep-pre-commit/actions/workflows/test.yaml/badge.svg)](https://github.com/boidolr/ast-grep-pre-commit/actions/workflows/test.yaml)
[![pre-commit](https://img.shields.io/badge/pre--commit-hook-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
================


Minimal git hook to run [ast-grep](https://github.com/ast-grep/ast-grep) based on the [pre-commit](https://github.com/pre-commit/pre-commit) framework.

## Using ast-grep-pre-commit with pre-commit

Add this to your `.pre-commit-config.yaml`:
```
  - repo: https://github.com/boidolr/ast-grep-pre-commit
    rev: 0.40.4  # Use the ref you want to point at
    hooks:
      - id: ast-grep
```

Note that, by default, only rules with a severity of "error" will lead to the commit hook failing.
If you wish to handle rules differently, set their error level in the rule configuration or via `--error`.


### Automatically execute rewrites

```
  - repo: https://github.com/boidolr/ast-grep-pre-commit
    rev: 0.40.4
    hooks:
      - id: ast-grep
        args: ["--update-all"]
```


### Provide explicit configuration

```
  - repo: https://github.com/boidolr/ast-grep-pre-commit
    rev: 0.40.4
    hooks:
      - id: ast-grep
        args: ["--config", "/some/path/sgconfig.yaml"]
```

### Overwrite ast-grep version

The hook version mirrors the version of ast-grep.
If for any reason you want up- or downgrade the ast-grep version used by the hook, for example to get an update before the hook was published, you can do so:
```
  - repo: https://github.com/boidolr/ast-grep-pre-commit
    rev: 0.40.4
    hooks:
      - id: ast-grep
        additional_dependencies: ["@ast-grep/cli@0.38.1"]  # set the desired version
```


## How to write rules

See https://ast-grep.github.io/ for details on `ast-grep` and how to write linters and rewriters.
