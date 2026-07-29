# Swap3D OpenAPI

The canonical, machine-readable contract for the public
[Swap3D developer API](https://swap3d.studio/developer-api).

This repository describes the API-key interface used by the official
[Swap3D CLI](https://github.com/swap3d/swap3d-cli) and future SDKs and
integrations. Dashboard, authentication, billing, and internal operations
endpoints are intentionally excluded.

## API Surface

| Operation | Endpoint |
| --- | --- |
| Get capabilities | `GET /openapi/formats` |
| Get monthly usage | `GET /openapi/usage` |
| Submit a conversion | `POST /openapi/convert` |
| Get conversion status | `GET /openapi/convert/status/{jobId}` |

The production base URL is:

```text
https://api.swap3d.studio/api/v1
```

Authenticated operations use a Swap3D API key as a Bearer token.

## Validate The Contract

Node.js 22.12 or newer is required.

```shell
npm ci
npm test
```

`npm test` lints the source contract, produces a bundled specification at
`dist/openapi.yaml`, and confirms that the committed `openapi.json` artifact
matches `openapi.yaml`. SDKs and contract checks should consume the generated
JSON rather than maintaining another schema by hand.

Pull requests are also checked for breaking changes with
[oasdiff](https://github.com/oasdiff/oasdiff). Intentional breaking changes
must use a new API version rather than silently changing the existing
contract.

## Contributing

Keep the contract aligned with deployed behavior. Changes to endpoints,
authentication, limits, formats, status values, or error responses must be
implemented and tested in `swap3d-studio` before this specification is
updated.

See [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## Security

Do not open a public issue for suspected vulnerabilities. Follow
[SECURITY.md](SECURITY.md) for private reporting.

## License

Apache-2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
