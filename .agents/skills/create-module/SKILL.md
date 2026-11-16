---
name: create-module
description: Scaffolds a new feature-based module with routes, validations, controller, model, service, and co-located tests.
---

# Create Feature Module

Use this skill when creating a new feature module in the backend or frontend.

## Steps
1. **Identify the target stack** (e.g., TypeScript/Node, NestJS, Python/FastAPI, React/Next.js) and follow its naming convention (`camelCase` for JS/TS functions/variables, `snake_case` for Python, `PascalCase` for classes, `UPPER_CASE` for constants).
2. **Create the module directory** under the project's modules/features folder.
3. **Scaffold backend layers** (when applicable):
   - `routes` — HTTP route definitions
   - `validations` — request/field validation schemas
   - `controller` — request/response handling
   - `model` — entity/schema/types
   - `service` — business logic
4. **Scaffold frontend service** (when applicable):
   - Extend or use the project's **base API client class** (inheriting base URL and shared config).
   - Export reusable service methods for components.
5. **Create co-located tests** inside the module directory covering the initial module functions.
6. **Verify**: Run the project's linter, typechecker, and the new module's tests.

