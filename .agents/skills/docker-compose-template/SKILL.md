---
name: docker-compose-template
description: Generates a Dockerfile and docker-compose.yml using .env ports, matching host:container ports, and $VARIABLE syntax.
---

# Docker & Docker Compose Template

Use this skill when containerizing a project or adding a new service.

## Rules
1. **Environment Variables**:
   - Define all service ports and credentials in `.env` (and document placeholders in `.env.example`).
   - Reference variables in `docker-compose.yml` using `$VARIABLE` syntax, **never** `"${VARIABLE}"`.
2. **Ports**:
   - Always map containers to the **exact same port on the host** (e.g., `$API_PORT:$API_PORT`).
3. **Best Practices**:
   - Include `env_file: .env` when services need environment variables.
   - Add `healthcheck` and `restart: unless-stopped` where appropriate.
   - Use multi-stage builds in `Dockerfile` and ensure `.env` is in `.dockerignore`.

