# AGENTS.md

This repository is the canonical public contract for the Swap3D developer
API.

## Rules

- Keep `openapi.yaml` aligned with implemented and tested production behavior.
- Do not add Dashboard, authentication, billing, Waffo, or internal operations
  endpoints.
- Treat operation IDs and response fields as public compatibility boundaries.
- Run `npm test` after changing the contract.
- Use ASCII unless existing content requires otherwise.
- Update `CHANGELOG.md` for behavior changes.

The implementation lives in the private `swap3d-studio` repository. Review
its OpenAPI routes, controllers, middleware, and tests before editing this
contract.
