# Contributing to OpenCanoeTiming

Thanks for your interest in contributing! Here's how we work.

## Issues First

Before starting work on a change, please make sure there is a related
**GitHub issue**. This helps us track what's being worked on and why.

- **Bug?** Open a bug issue describing what's wrong.
- **New feature or improvement?** Open a feature issue describing what
  you want to achieve and why.
- **Small fix** (typo, minor cleanup)? An issue is nice to have but not
  strictly required.

This is not a hard rule — use your judgment. The goal is to have a
clear record of *why* changes are made.

## Workflow

1. Pick or create an issue
2. Create a branch from `main`
3. Make your changes
4. Open a Pull Request
5. Get at least 1 approval from a core maintainer
6. Maintainer merges via squash merge

### Branch naming

Use a descriptive name, **prefix with the issue number is highly welcome**:

```
feat/12-start-list-panel
fix/34-penalty-display
docs/update-readme
```

### Commit messages

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
type: short description in imperative mood

Optional longer explanation of what and why.
```

Types: `feat`, `fix`, `docs`, `refactor`, `ci`, `test`, `chore`

Don't worry too much about individual commit messages — we use squash
merge, so the final commit message can be cleaned up at merge time.

### Pull Requests

- Describe **what** changed and **why**
- Reference the related issue (e.g. `Closes #12`)
- Before opening, make sure these pass (where applicable):
  - `npm run lint`
  - `npm run build`
  - `npm test`

## Language conventions

- **Code** (variables, functions, comments): English
- **Commit messages**: English
- **Issues, PR descriptions, discussions**: Czech is fine if no non-czech speaker is involved
- **Documentation**: English 

## Questions?

Open an issue or ask in team chat before starting work on larger changes.
