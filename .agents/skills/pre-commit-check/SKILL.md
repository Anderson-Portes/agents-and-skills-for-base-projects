---
name: pre-commit-check
description: Runs linters, strict type checks, tests, and audits diffs against coding-standards.md before committing.
---

# Pre-Commit Check

Use this skill before creating a commit or opening a PR.

## Checklist
1. **Linter & Formatter**: Run the project's configured linter and formatter (e.g., ESLint, Prettier, Ruff, Black).
2. **Type Check**: Run strict type checking and ensure zero `any` / `as any` usages were introduced.
3. **Rule Audit** (check `git diff`):
   - No `else` after `return` (use early returns).
   - No unnecessary `switch` where an object mapper is cleaner.
   - No hardcoded credentials or secrets.
   - In `docker-compose.yml`, all env vars use `$VARIABLE` (not `"${VARIABLE}"`) and ports match host:container (`$PORT:$PORT`).
4. **Tests**: Run the test suite and confirm all module tests pass, including tests for any newly added functions.

