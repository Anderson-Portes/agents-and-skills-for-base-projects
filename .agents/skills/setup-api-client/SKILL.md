---
name: setup-api-client
description: Scaffolds a frontend base API client class (base URL from env, headers, auth interceptors, error handling) and a reusable feature service.
---

# Setup Frontend API Client

Use this skill when setting up frontend-to-backend communication.

## Steps
1. **Create the Base API Client class** (e.g., `BaseApiClient` in `src/services/baseApiClient.ts` or equivalent):
   - Load the base URL from environment variables (never hardcode it).
   - Configure default headers (`Content-Type: application/json`, etc.).
   - Add request/response interceptors for auth tokens and normalized error handling.
   - Use strict typing (no `any` or `as any`).
2. **Create a Feature Service** inheriting from or instantiating `BaseApiClient` so multiple components can reuse the same API methods.
3. **Create co-located tests** for the base client and feature service.

