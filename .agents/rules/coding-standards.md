---
trigger: always_on
---

# Coding & Architecture Standards

## 1. Architecture & Layering
- **Feature-based modular architecture** (similar to NestJS): organize the application by feature modules rather than a rigid global folder tree.
- Separate each backend module into clear layers:
  - **Routes** (endpoint definitions)
  - **Validations** (input/field validation)
  - **Controller** (request/response handling)
  - **Model** (data structures / schemas / entities)
  - **Service** (business logic)
- **Shared utilities**:
  - Any function reused across multiple files must live in a `utils/` folder.
  - When a specific domain accumulates many utility functions (e.g., string manipulation, date formatting), group them into a dedicated **class** instead of loose functions.
- **Frontend API communication**:
  - Create reusable **service layers** for backend communication so multiple components can share them.
  - Use a **base API client class** (with base URL, headers, interceptors/error handling) that feature services inherit from or instantiate.

## 2. Naming Conventions
- **Classes**: `PascalCase`
- **Variables & Functions**: `camelCase` (use `snake_case` in Python projects)
- **Constants**: `UPPER_CASE` always
- **Language**: Write code, identifiers, and comments in **English** by default, unless translating a domain term would make it less intuitive.

## 3. Control Flow & Typing
- **No `else` after `return`**: Always use early returns; leave the `if` block with `return` and omit `else`.
- **`switch` vs. Object Mapper**: Use `switch` only when it is clearly optimal; otherwise, prefer an object/dictionary mapper.
- **Strict typing**: Never use `any` or `as any` (or equivalent type-escape hatches).
- **Linters**: Always configure and follow the standard linter/formatter for each language.

## 4. Testing
- **Co-located module tests**: Whenever a module is implemented, create its tests inside that module's directory (both frontend and backend).
- **Incremental test updates**: Whenever a new function is added to a module, add its tests to that module's existing test file.

## 5. Environment, Credentials & Docker
- **Credentials**: Never hardcode secrets or credentials; always load them from environment variables (`.env`).
- **Docker & Docker Compose**:
  - Define service ports in `.env` and map containers to the **same port on the host** (e.g., `$API_PORT:$API_PORT`).
  - Always reference environment variables in `docker-compose.yml` using `$VARIABLE` syntax, **not** `"${VARIABLE}"`.

