# Python

## Documentation

See [documentation](https://github.com/specifysystems/code-principles/blob/main/language/README.md#documentation)
in the general section first.

For in-line comments, use Google style of Python DocStrings.
Use [DargLint](#Darglint) and [PyDocStyle](#PyDocStyle) pre-commit hooks for
enforcing compliance and detecting style issues in DocStrings.

## Pre-commit hooks

### Black

Python linter

Example config:

```yaml
- repo: https://github.com/psf/black
  rev: 21.11b1
  hooks:
    - id: black
      args:
        - --line-length=72
```

[Documentation](https://github.com/psf/black)

### Flake8

Python formatter

Example config:

```yaml
- repo: https://gitlab.com/pycqa/flake8
  rev: 3.9.2
  hooks:
    - id: flake8
      additional_dependencies:
        - flake8-bugbear
          args:
      # these settings are needed to make flake8 compatible with black
        - --max-line-length=88
        - --select=C,E,F,W,B,B950
        - --extend-ignore=E203,E501
```

[Documentation](https://gitlab.com/pycqa/flake8)

### Darglint

DocStyle linter

Example config:

```yaml
- repo: https://github.com/terrencepreilly/darglint
  rev: v1.8.1
  hooks:
    - id: darglint
      args:
        - -v 2
```

[Documentation](https://github.com/terrencepreilly/darglint)

### PyDocStyle

Additional linter (complementary to Darglint)

Example config:

```yaml
- repo: https://github.com/PyCQA/pydocstyle
  rev: 6.1.1
  hooks:
    - id: pydocstyle
```

[Documentation](https://github.com/PyCQA/pydocstyle)

### PyUpgrade

Automatically upgrade syntax for newer versions of Python

Example config:

```yaml
- repo: https://github.com/asottile/pyupgrade
  rev: v2.29.1
  hooks:
    - id: pyupgrade
```

[Documentation](https://github.com/asottile/pyupgrade)

### Setup Config Format

Apply a consistent format to `setup.cfg` files

Example config:

```yaml
- repo: https://github.com/asottile/setup-cfg-fmt
  rev: v1.20.0
  hooks:
    - id: setup-cfg-fmt
```

[Documentation](https://github.com/asottile/pyupgrade)

### Python Dependencies Safety Check

Checks for known vulnerabilities in used dependencies

Example config:

```yaml
- repo: https://github.com/Lucas-C/pre-commit-hooks-safety
  rev: v1.2.2
  hooks:
    - id: python-safety-dependencies-check
```

[Documentation](https://github.com/Lucas-C/pre-commit-hooks-safety)

### 