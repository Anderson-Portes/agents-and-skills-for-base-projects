# Base Project Agents, Skills & Rules

Template and plugin containing standardized coding rules, architecture guidelines, specialized agents, and reusable skills for new projects.

## How to Use

### Option 1: Copy as a Project Template
Copy `.agents/` into the root of your new project:
```bash
cp -r .agents /path/to/your-new-project/
```

### Option 2: Install as a Global Plugin
Symlink or copy this repository into `~/.gemini/config/plugins/base-project-standards`:
```bash
ln -s "$(pwd)" ~/.gemini/config/plugins/base-project-standards
```

## Included Structure

- **`.agents/rules/coding-standards.md`**: Always-on rules for architecture, naming, control flow, strict typing, testing, Docker, and environment variables.
- **`.agents/agents/`**:
  - `architect.md` — Validates feature-based modular architecture and layer separation.
  - `code-reviewer.md` — Audits code against all naming, typing, control flow, and security rules.
  - `test-engineer.md` — Creates and updates co-located module tests (frontend & backend).
  - `refactorer.md` — Refactors code to follow early returns, object mappers, and utility classes.
- **`.agents/skills/`**:
  - `create-module` — Scaffolds a new feature module with all required layers and tests.
  - `pre-commit-check` — Runs linters, type checks, tests, and rule audits before committing.
  - `project-setup` — Sets up `.env.example`, `docker-compose.yml` (`$VAR` syntax), and base configs.
  - `conventional-commit` — Formats commits with `feat:`, `fix:`, `chore:`, etc.

