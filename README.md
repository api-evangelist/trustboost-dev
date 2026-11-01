# TrustBoost PII Sanitizer

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

TrustBoost PII Sanitizer is a pay-per-call "privacy firewall" for autonomous AI agent pipelines, built and operated by an individual developer (Teodoro Crispin, GitHub teodorofodocrispin-cmyk) and served entirely from https://api.trustboost.dev — the apex trustboost.dev has no DNS record. An agent POSTs text to /sanitize and gets it back with emails, phone numbers, national IDs (RFC, CUIT, CPF, CNPJ, Personalausweis, マイナンバー, NIR, Codice Fiscale, RRN and more across 8 languages), API keys and financial data replaced by [REDACTED], plus a safety_score, a risk_category and an entity list; five context modes (general, legal, financial, medical, code) tune the redaction. There is no account and no API key: 50 free calls per wallet with tx_hash=TRIAL, a free 3-per-hour preview, then x402 payment in USDC on Base or Solana ($0.01 per call or a 149 USDC prepaid bundle of 10,000), with every paid sanitization anchored on Solana as a verifiable "Proof of Sanitization". The same service is exposed three ways from one host: a 9-operation OpenAPI 3.0.0 REST contract, a remote MCP server at /mcp (one tool, sanitize_pii), and an A2A-flavored agent card at /.well-known/agent-card.json with three skills. The provider's own privacy policy describes it as a learning prototype that sends raw text to OpenAI GPT-4o-mini for detection and has no certified security audit.

**Areas:** Privacy · PII Redaction · Data Protection · LLM Security · AI Safety · Agents · A2A · MCP · x402 · Agentic Commerce · Solana · Compliance

## TrustBoost PII Sanitizer on APIs.io

Everything profiled for TrustBoost PII Sanitizer is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/trustboost-dev/](https://apis.io/providers/trustboost-dev/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [TrustBoost MCP Server](https://apis.io/apis/trustboost-dev/trustboost-mcp-server/) — Remote Model Context Protocol server at https://api.trustboost.dev/mcp (HTTP JSON-RPC 2.0, protocol version 2024-11-05, serverInfo trustboost 2.6.0).…
- [TrustBoost A2A Agent](https://apis.io/apis/trustboost-dev/trustboost-a2a-agent/) — Agent2Agent surface: an agent card served from https://api.trustboost.dev/.well-known/agent-card.json (version 2.6.0, no protocolVersion, capabilities…
- [TrustBoost PII Sanitizer Budget API](https://apis.io/apis/trustboost-dev/trustboost-dev-budget-api/) — The Budget API from TrustBoost PII Sanitizer — 1 operation(s) for budget.
- [TrustBoost PII Sanitizer Health API](https://apis.io/apis/trustboost-dev/trustboost-dev-health-api/) — The Health API from TrustBoost PII Sanitizer — 1 operation(s) for health.
- [TrustBoost PII Sanitizer MCP API](https://apis.io/apis/trustboost-dev/trustboost-dev-mcp-api/) — The Mcp API from TrustBoost PII Sanitizer — 1 operation(s) for mcp.
- [TrustBoost PII Sanitizer Message API](https://apis.io/apis/trustboost-dev/trustboost-dev-message-api/) — The Message API from TrustBoost PII Sanitizer — 1 operation(s) for message.
- [TrustBoost PII Sanitizer Sanitize API](https://apis.io/apis/trustboost-dev/trustboost-dev-sanitize-api/) — The Sanitize API from TrustBoost PII Sanitizer — 2 operation(s) for sanitize.
- [TrustBoost PII Sanitizer Score API](https://apis.io/apis/trustboost-dev/trustboost-dev-score-api/) — The Score API from TrustBoost PII Sanitizer — 1 operation(s) for score.
- [TrustBoost PII Sanitizer Verify API](https://apis.io/apis/trustboost-dev/trustboost-dev-verify-api/) — The Verify API from TrustBoost PII Sanitizer — 1 operation(s) for verify.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [trustboost-dev-mcp.yml](https://apis.io/servers/trustboost-dev/trustboost-dev-mcp-yml/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Trustboost Dev Openapi Overlay](https://apis.io/overlays/trustboost-dev/trustboost-dev-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Trustboost Dev Authentication](https://apis.io/security/trustboost-dev/trustboost-dev-authentication/)
- [Trustboost Dev Domain Security](https://apis.io/security/trustboost-dev/trustboost-dev-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Trustboost Dev Plans Pricing](https://apis.io/plans/trustboost-dev/trustboost-dev-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Trustboost Dev Rate Limits](https://apis.io/rate-limits/trustboost-dev/trustboost-dev-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://api.trustboost.dev/)
- [Documentation](https://github.com/teodorofodocrispin-cmyk/TrustBoost-PII-Sanitizer)
- [Getting started](https://github.com/teodorofodocrispin-cmyk/TrustBoost-PII-Sanitizer/blob/main/AGENTS.md)
- [API reference](https://api.trustboost.dev/openapi.json)
- [Pricing](https://api.trustboost.dev/pricing.md)
- [Support](https://github.com/teodorofodocrispin-cmyk/TrustBoost-PII-Sanitizer/issues)
- [Terms of service](https://github.com/teodorofodocrispin-cmyk/TrustBoost-PII-Sanitizer/blob/main/PRIVACY.md)
- [Privacy policy](https://github.com/teodorofodocrispin-cmyk/TrustBoost-PII-Sanitizer/blob/main/PRIVACY.md)
- [GitHub](https://github.com/teodorofodocrispin-cmyk)

## API Evangelist rating

**Kin Score 50.2** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 41.7 |
| Contract governance | 18.2 |
| Operational transparency | 23.7 |
| Developer ergonomics | 59.5 |
| Access clarity | 63.2 |

**Agent readiness 31.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | flavored (partial credit) |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 36.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/trustboost-dev/](https://apis.io/providers/trustboost-dev/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for TrustBoost PII Sanitizer: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/trustboost-dev/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
