# JavaScript

Code-style guidelines and best practices for JavaScript (including
TypeScript and React)

## Pre-commit hooks

### Prettier

Highly opinionated formatter

Example config:

```yaml
- repo: https://github.com/pre-commit/mirrors-prettier
  rev: v2.5.0
  hooks:
    - id: prettier
      additional_dependencies:
        - prettier@2.5.0
        - '@prettier/plugin-xml@^0.13.1'
        - prettier-plugin-package@^1.3.0
        - prettier-plugin-sh@^0.8.1
        - prettier-plugin-tailwind-css@^1.5.0
        - prettier-plugin-firebase-database@^1.0.1
```

Also, add this to `package.json`:

```json
{
  "devDependencies": {
    "@maxxxxxdlp/prettier-config": "^1.0.3",
    "prettier": "^2.3.1"
  },
  "prettier": "@maxxxxxdlp/prettier-config"
}

```

[Documentation](https://prettier.io/)

### StyleLint

CSS Linter

Example config:

```yaml
- repo: https://github.com/awebdeveloper/pre-commit-stylelint
  rev: 0.0.2
  hooks:
    - id: stylelint
      files: \.(css|scss|sass|js|jsx|ts|tsx)$
      additional_dependencies:
        - stylelint@^14.1.0
        - stylelint-config-prettier@^9.0.3
        - stylelint-config-standard@^24.0.0
```

Also, add the following devDependencies to `package.json`:

```yaml
    "@maxxxxxdlp/stylelint-config": "^1.0.0",
    "@stylelint/postcss-css-in-js": "^0.37.2",
    "stylelint": "^14.1.0",
```

And finally, create `.stylelintrc.js ` in the same directory as
`package.json`

```javascript
'use strict';

module.exports = {
  extends: '@maxxxxxdlp/stylelint-config',
  rules: {},
  overrides: [
    {
      files: ['**/*.ts', '**/*.tsx', '**/*.js', '**/*.jsx'],
      customSyntax: '@stylelint/postcss-css-in-js',
    }
  ],
  ignoreFiles: [
    '**/*.md',
  ]
};
```

### ESLint

Highly customizable JavaScript (and TypeScript) linter

Example config:

```yaml
  - repo: https://github.com/pre-commit/mirrors-eslint
    rev: v8.4.1
    hooks:
      - id: eslint
        types: [text]
        types_or: [javascript, jsx, ts, tsx]
        additional_dependencies:
          - '@maxxxxxdlp/eslint-config@^1.0.9'
```

Also, add the following devDependencies to `package.json`:

```yaml
    "@maxxxxxdlp/eslint-config": "^1.0.9",
    "@rushstack/eslint-patch": "^1.1.0",
    "eslint": "^7.32.0",
```

And create `.eslintrc.js` in the same directory as `package.json`:

```javascript
require('@rushstack/eslint-patch/modern-module-resolution');

module.exports = {
  root: true,
  parser: '@typescript-eslint/parser',
  parserOptions: {
    project: './tsconfig.eslint.json',
  },
  env: {
    browser: true,
    node: true,
  },
  extends: ['@maxxxxxdlp/eslint-config'],
  rules: {
    '@typescript-eslint/no-empty-interface': 'off',
    '@next/next/no-img-element': 'off',
  },
};

```