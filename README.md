# Qorevia

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

Qorevia ("Qorevia Market Intelligence", operated from api.flowhomes.eu) is an agent-native, pay-per-call API seller: thirteen deterministic market-intelligence, data-profiling and developer utility tools — live XAUUSD (gold) quote, OHLCV bars and computed market state read from a read-only MetaTrader 5 terminal, trading-session state in Europe/Vienna time, stop/target risk levels, a strategy robustness grade, tick PnL, OHLCV state, CSV and JSON structural profiling, JWT decode, EVM address syntax and regex testing — each priced between $0.0025 and $0.05 and settled per call in USDC on Base Mainnet (eip155:8453) through the x402 v2 protocol (HTTP 402 -> pay -> retry with PAYMENT-SIGNATURE), with no accounts and no API keys. Discovery is free and unusually complete: an OpenAPI 3.1.0 contract at /openapi.json, an x402 manifest at /.well-known/x402, a remote MCP server at /mcp (four free finder/router/catalog tools, listed in the Official MCP Registry), an A2A 1.0 agent card at /.well-known/agent-card.json backed by a live JSON-RPC endpoint at /a2a, a skill.md, an llms.txt, a natural-language finder (/api/find) and a "Founders Network" whose tiers derive from verified x402 payment history. The registrable domain flowhomes.eu does not serve a website (TLS handshake fails; HTTP returns Cloudflare error 1001), so every surface lives on api.flowhomes.eu.

**Areas:** Market Data · Gold · XAUUSD · Trading · Finance · Quantitative Research · Risk Management · Data Profiling · Developer Tools · x402 · USDC · Base L2

## Qorevia on APIs.io

Everything profiled for Qorevia is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/flowhomes-eu/](https://apis.io/providers/flowhomes-eu/)** — or go straight to one of the APIs or properties below.

### APIs (24)

- [Qorevia Universal Agent Gateway (MCP + A2A)](https://apis.io/apis/flowhomes-eu/qorevia-universal-agent-gateway/) — The free discovery and routing layer in front of the paid tools, served from the same origin. MCP: https://api.flowhomes.eu/mcp is POST-only Streamable HTTP…
- [Qorevia A2a API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-a2a-api/) — The A2a API from Qorevia — 1 operation(s) for a2a.
- [Qorevia Amplifier API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-amplifier-api/) — The Amplifier API from Qorevia — 1 operation(s) for amplifier.
- [Qorevia Backtest API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-backtest-api/) — The backtest API from Qorevia — 1 operation(s) for backtest.
- [Qorevia Catalog API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-catalog-api/) — The Catalog API from Qorevia — 1 operation(s) for catalog.
- [Qorevia Club API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-club-api/) — The Club API from Qorevia — 6 operation(s) for club.
- [Qorevia CSV API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-csv-api/) — The CSV API from Qorevia — 1 operation(s) for csv.
- [Qorevia Data API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-data-api/) — The data API from Qorevia — 2 operation(s) for data.
- [Qorevia Developer Tools API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-developer-tools-api/) — The developer-tools API from Qorevia — 2 operation(s) for developer-tools.
- [Qorevia Distribution API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-distribution-api/) — The Distribution API from Qorevia — 1 operation(s) for distribution.
- [Qorevia Finance API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-finance-api/) — The finance API from Qorevia — 7 operation(s) for finance.
- [Qorevia Find API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-find-api/) — The Find API from Qorevia — 1 operation(s) for find.
- [Qorevia Gold API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-gold-api/) — The gold API from Qorevia — 3 operation(s) for gold.
- [Qorevia JSON API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-json-api/) — The JSON API from Qorevia — 1 operation(s) for json.
- [Qorevia Magnet API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-magnet-api/) — The Magnet API from Qorevia — 2 operation(s) for magnet.
- [Qorevia MCP API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-mcp-api/) — The Mcp API from Qorevia — 1 operation(s) for mcp.
- [Qorevia Onchain API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-onchain-api/) — The onchain API from Qorevia — 1 operation(s) for onchain.
- [Qorevia Quant API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-quant-api/) — The quant API from Qorevia — 1 operation(s) for quant.
- [Qorevia Risk API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-risk-api/) — The risk API from Qorevia — 1 operation(s) for risk.
- [Qorevia Route API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-route-api/) — The Route API from Qorevia — 1 operation(s) for route.
- [Qorevia Trading API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-trading-api/) — The trading API from Qorevia — 1 operation(s) for trading.
- [Qorevia Try API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-try-api/) — The Try API from Qorevia — 1 operation(s) for try.
- [Qorevia Utility API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-utility-api/) — The utility API from Qorevia — 5 operation(s) for utility.
- [Qorevia .well Known API](https://apis.io/apis/flowhomes-eu/flowhomes-eu-well-known-api/) — The .well Known API from Qorevia — 5 operation(s) for .well known.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [flowhomes-eu-mcp.yml](https://apis.io/servers/flowhomes-eu/flowhomes-eu-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Flowhomes Eu Agentic Access](https://apis.io/agentic-access/flowhomes-eu/flowhomes-eu-agentic-access/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Flowhomes Eu Openapi Overlay](https://apis.io/overlays/flowhomes-eu/flowhomes-eu-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Flowhomes Eu Authentication](https://apis.io/security/flowhomes-eu/flowhomes-eu-authentication/)
- [Flowhomes Eu Domain Security](https://apis.io/security/flowhomes-eu/flowhomes-eu-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Flowhomes Eu Plans Pricing](https://apis.io/plans/flowhomes-eu/flowhomes-eu-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Flowhomes Eu Rate Limits](https://apis.io/rate-limits/flowhomes-eu/flowhomes-eu-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://api.flowhomes.eu/)
- [Documentation](https://api.flowhomes.eu/skill.md)
- [Getting started](https://api.flowhomes.eu/api/try)
- [API reference](https://api.flowhomes.eu/)
- [Pricing](https://api.flowhomes.eu/)

## API Evangelist rating

**Kin Score 36.1** — thin · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 63.3 |
| Contract quality | 41.1 |
| Contract governance | 18.2 |
| Operational transparency | 15.8 |
| Developer ergonomics | 47.6 |
| Access clarity | 31.6 |

**Agent readiness 39.6** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 21.3** — Securities & Market Data

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/flowhomes-eu/](https://apis.io/providers/flowhomes-eu/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Qorevia: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/flowhomes-eu/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
