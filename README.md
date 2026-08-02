# Qualia

Qualia (Qualia Labs, Inc.) is a digital real estate closing platform. Its cloud-based title, escrow and settlement software brings title agents, lenders, real estate agents and consumers onto one secure system of record — across Core, Connect, Shield, Marketplace, Assure, Atlas, Clear and Resware.

The **Qualia API** (launched August 2022) is a read-write **GraphQL** interface at `https://api.qualia.com/graphql`. It lets proptech companies, lenders and enterprise title operations place and track title orders, exchange messages and documents, and pull order, accounting and contact data for custom reporting and executive dashboards. Authentication is HTTP Basic; authorization is by **capability gates** enabled per organization.

- Website: https://www.qualia.com/
- API: https://www.qualia.com/qualia-api/
- API Terms: https://www.qualia.com/api-terms/
- Status: https://status.qualia.com/
- Trust Center: https://www.qualia.com/trust/

## Artifacts

| Dir | File | Method |
|---|---|---|
| `graphql/` | `qualia-graphql.yml` | probed — endpoint confirmed, introspection auth-gated (401) |
| `authentication/` | `qualia-authentication.yml` | searched — HTTP Basic + capability gates |
| `conventions/` | `qualia-conventions.yml` | searched |
| `errors/` | `qualia-error-codes.yml` | probed — GraphQL error envelope observed |
| `lifecycle/` | `qualia-lifecycle.yml` | searched — 12-month version window, status page |
| `conformance/` | `qualia-conformance.yml` | searched — SOC 2 Type II, ISO 27001, ALTA Pillar 3 |
| `security/` | `qualia-domain-security.yml`, `qualia-trust-center.yml`, `qualia-vulnerability-disclosure.yml` | probed / searched |
| `well-known/` | `qualia-security.txt`, `qualia-well-known.yml` | searched |
| `mcp/` | `qualia-mcp.yml` | searched — **third-party only**, no first-party server |
| `llms/` | `qualia-llms.txt` | generated |

## Not published by Qualia (verified 2026-08-02)

- **No OpenAPI/Swagger** — `api.qualia.com/openapi.json`, `/swagger.json`, `/docs` all 404. The contract is GraphQL only, and the SDL requires authenticated introspection.
- **No A2A agent card** — `/.well-known/agent-card.json` and the legacy `/.well-known/agent.json` return 404 on every Qualia host.
- **No first-party MCP server, SDK, CLI, or package-registry client library.**
- **No public sandbox, dated API changelog, webhook/event surface, or OAuth.**
- Reference documentation is gated behind partner onboarding (`help.qualia.com` is a Skilljar login).
