# Language-specific information 

## Contents

This file contains generic information that is not specific to a single
language.

Language-specific information:
- [JavaScript](./language/javascript)
- [Python](./language/python)

## Documentation

Create `README.md` files in key folders of the project. The content of
this file would be rendered whenever that folder is opened in an IDE
or GitHub.

Such file may contain:
 - High level overview of the files in the directory
 - Major design decisions and the reason behind them

Additionally, each file should contain in-line documentation (at the top
of the file, and a comment for each function). For more details, see language
specific guidelines.

## Pre-commit hooks

### Regex-Blacklist

Prevents a commit if changed files matched one of the regex statements
from the blacklist dictionary.

Useful for making sure the following things don't get committed
accidentally:

 - Unresolved `FIXME:` comments
 - Unresolved merge conflicts (`<<<< HEAD`)
 - Secret keys
 - Changes to the config file (`DEVELOPMENT=true)

Example config:

```yaml
- repo: https://github.com/maxxxxxdlp/pre-commit
  rev: v1.0.5
  hooks:
    - id: regex-blacklist
      args:
        - specifyweb/frontend/js_src/lib/tests/regex-blacklist.txt
```

[Documentation](https://github.com/maxxxxxdlp/pre-commit)

### Spell checker

Example config:

```yaml
- repo: https://github.com/codespell-project/codespell
  rev: v2.1.0
  hooks:
    - id: codespell
      args:
        - --skip="./node_modules/,package-lock.json,./.idea/"
```

[Documentation](https://github.com/codespell-project/codespell)

### Misc utility hooks

Detailed description of each hook is provided in the documentation.

Example config:

```yaml
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.0.1
  hooks:
    - id: trailing-whitespace
    - id: end-of-file-fixer
    - id: check-added-large-files
    - id: check-case-conflict
    - id: check-docstring-first
    - id: check-xml
    - id: check-shebang-scripts-are-executable
    - id: check-merge-conflict
    - id: check-symlinks
    - id: detect-private-key
    - id: mixed-line-ending
    - id: requirements-txt-fixer
    - id: fix-byte-order-marker
    - id: fix-encoding-pragma
    - id: forbid-new-submodules
```

[Documentation](https://github.com/pre-commit/pre-commit-hooks)

### Markdown lint

Strict markdown linter

Example config:

```yaml
- repo: https://github.com/markdownlint/markdownlint
  rev: v0.11.0
  hooks:
    - id: markdownlint
      files: \.md$
      args:
        - --git-recurse
```

[Documentation](https://github.com/markdownlint/markdownlint)

### Git Commit Message Style

Example config:

```yaml
- repo: https://github.com/jorisroovers/gitlint
  rev: v0.16.0
  hooks:
    - id: gitlint
```

[Documentation](https://github.com/jorisroovers/gitlint)

### Dockerfile and Docker-compose check

Example config:

```yaml
- repo: https://github.com/IamTheFij/docker-pre-commit
  rev: v2.0.1
  hooks:
    - id: docker-compose-check
```


### JSCPD

Duplicate code detection

```yaml
- repo: https://github.com/maxxxxxdlp/mirrors-jscpd
  rev: v3.3.26
  hooks:
    - id: jscpd
      types: [text]
```

[Documentation](https://github.com/kucherenko/jscpd)