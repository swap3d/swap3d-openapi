# Contributing

## Contract Changes

Open an issue before changing authentication, removing fields, narrowing
accepted values, or otherwise changing existing client behavior.

Every contract change must:

- match implemented and tested production behavior
- preserve operation IDs unless a new operation replaces the old one
- include descriptions for new operations, parameters, and schemas
- pass Redocly validation
- pass the oasdiff breaking-change check
- update the changelog when behavior changes

Run the checks locally with:

```shell
npm ci
npm test
```

Do not add Dashboard, authentication, billing, Waffo, or internal operations
endpoints to this public developer contract.
