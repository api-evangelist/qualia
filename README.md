# Qualia

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
