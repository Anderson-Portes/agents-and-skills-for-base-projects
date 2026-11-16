---
name: conventional-commit
description: Creates Git commits using Conventional Commits prefixes (feat, fix, chore, refactor, test, docs) in the project's defined language.
---

# Conventional Commit

Use this skill when committing changes to Git.

## Format
```text
<type>(<scope>): <short description>
```

Common types:
- `feat`: New feature or module
- `fix`: Bug fix
- `refactor`: Code change that neither fixes a bug nor adds a feature
- `test`: Adding or updating module tests
- `chore`: Build, dependencies, Docker, or config changes
- `docs`: Documentation updates

## Rules
1. Use the language defined for the project (default: English, unless the user specifies another language).
2. Keep the subject line concise and imperative.
3. Run `pre-commit-check` before committing if not already done.

