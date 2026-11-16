---
name: project-setup
description: Initializes base project configuration, .env.example, docker-compose.yml with $VAR syntax, and standard linters.
---

# Project Setup

Use this skill when starting a new project or standardizing an existing one.

## Steps
1. **Environment variables**:
   - Create `.env.example` with all required service ports and credential placeholders.
   - Ensure `.env` is listed in `.gitignore`.
2. **Docker Compose** (when using Docker):
   - Map container ports to the exact same host port defined in `.env` (e.g., `$API_PORT:$API_PORT`).
   - Always use `$VARIABLE` syntax, never `"${VARIABLE}"`.
3. **Linter & Strict Typing**:
   - Configure the language's standard linter and formatter.
   - Enable strict type checking (e.g., `"strict": true` in `tsconfig.json`, disallowing `any`).
4. **Frontend Base API Client** (if frontend):
   - Create a base API client class configured with the base URL from environment variables so all feature services can inherit from it.

