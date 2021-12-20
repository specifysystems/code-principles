# Dependabot

Scan dependencies for out-of-life and security vulnerabilities.

(This is not actually a GitHub Action)

To configure, create a `.github` folder in the repository and add a
`dependabot.yml` file:

```yml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "monthly"
    assignees:
      - "maxxxxxdlp"
  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "monthly"
```