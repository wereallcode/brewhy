# Contributing

This guide covers the development setup, checks and CI.

## 1. Setup

Run this once after cloning to install dependencies and enable the Git hooks.

```bash
npm ci
```

## 2. Checks

Every commit formats and lints staged files and checks the commit message.

Run all checks manually with this command.

```bash
npm run lint && npm run format:check && npm run typecheck && npm test && npm run build
```

## 3. CI

CI runs the checks on Linux with Node.js 22 and 24.

Linux runners do not include `zsh`, so CI installs it for the installer tests.

Every push to `master` then runs semantic-release, which releases `feat`, `fix` and `perf` commits and breaking changes.
