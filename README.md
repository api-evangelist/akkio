# Akkio

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

Akkio is a no-code predictive AI and AI-workflow-automation platform built for media agencies and data providers. Teams use it to activate data across the campaign lifecycle: audience segmentation, propensity modeling, RFM analysis, media-mix modeling, performance measurement, and campaign-strategy development, all from unified intelligence. Beyond the app, Akkio ships a developer REST API on https://api.akkio.com in two generations: the legacy /v1 datasets and models routes (api_key in query or body), and the current "Akkio Public API (Beta)" at /api/v1, which covers projects, asynchronous model training and Chat Explore natural-language querying behind an X-API-Key header. Akkio publishes its own OpenAPI 3.1.0 document at /api/v1/api.yaml with a Swagger UI at /api/v1/docs and documents generating clients from it; the two first-party SDKs (PyPI and npm `akkio`) cover only the legacy surface and have not been released since 2021. The company is SOC 2 Type 2 and HIPAA compliant (verified via Drata).

**Areas:** Company · Ai Apps · Machine Learning · Predictive Analytics · No-Code · Data Science · Marketing · Media · Audience Modeling · Predictions

## Akkio on APIs.io

Everything profiled for Akkio is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/akkio/](https://apis.io/providers/akkio/)** — or go straight to one of the APIs or properties below.

### APIs (78)

- [Akkio Datasets API](https://apis.io/apis/akkio/akkio-datasets-api/) — Legacy v1 datasets surface. Create a dataset, append rows, set field types, parse fields, list and delete. Authenticated with an api_key query parameter on…
- [Akkio Models API](https://apis.io/apis/akkio/akkio-models-api/) — Legacy v1 models surface. List trained models and POST rows to a model to receive predictions with per-class probabilities. Akkio's own docs describe the…
- [Akkio Ad Analytics API](https://apis.io/apis/akkio/akkio-ad-analytics-api/) — The Ad Analytics API from Akkio — 32 operation(s) for ad analytics.
- [Akkio Admin API](https://apis.io/apis/akkio/akkio-admin-api/) — The admin API from Akkio — 2 operation(s) for admin.
- [Akkio API Specification API](https://apis.io/apis/akkio/akkio-api-specification-api/) — The API Specification API from Akkio — 2 operation(s) for api specification.
- [Akkio Async Job API](https://apis.io/apis/akkio/akkio-async-job-api/) — The Async Job API from Akkio — 2 operation(s) for async job.
- [Akkio Audience API](https://apis.io/apis/akkio/akkio-audience-api/) — The audience API from Akkio — 27 operation(s) for audience.
- [Akkio Audiences API](https://apis.io/apis/akkio/akkio-audiences-api/) — The Audiences API from Akkio — 3 operation(s) for audiences.
- [Akkio Auth Integration API](https://apis.io/apis/akkio/akkio-auth-integration-api/) — The Auth Integration API from Akkio — 1 operation(s) for auth integration.
- [Akkio Chart API](https://apis.io/apis/akkio/akkio-chart-api/) — The chart API from Akkio — 4 operation(s) for chart.
- [Akkio Chat Explore API](https://apis.io/apis/akkio/akkio-chat-explore-api/) — The Chat Explore API from Akkio — 28 operation(s) for chat explore.
- [Akkio Chat Explore Chart Update API](https://apis.io/apis/akkio/akkio-chat-explore-chart-update-api/) — The Chat Explore Chart Update API from Akkio — 1 operation(s) for chat explore chart update.
- [Akkio Chat Explore Ratings API](https://apis.io/apis/akkio/akkio-chat-explore-ratings-api/) — The Chat Explore Ratings API from Akkio — 1 operation(s) for chat explore ratings.
- [Akkio Chat Explore Suggestions API](https://apis.io/apis/akkio/akkio-chat-explore-suggestions-api/) — The Chat Explore Suggestions API from Akkio — 1 operation(s) for chat explore suggestions.
- [Akkio Clone Lifecycle API](https://apis.io/apis/akkio/akkio-clone-lifecycle-api/) — The Clone Lifecycle API from Akkio — 1 operation(s) for clone lifecycle.
- [Akkio Cluster Suggestions API](https://apis.io/apis/akkio/akkio-cluster-suggestions-api/) — The Cluster Suggestions API from Akkio — 1 operation(s) for cluster suggestions.
- [Akkio Create Integration Output API](https://apis.io/apis/akkio/akkio-create-integration-output-api/) — The Create Integration Output API from Akkio — 1 operation(s) for create integration output.
- [Akkio Dashboard Name API](https://apis.io/apis/akkio/akkio-dashboard-name-api/) — The Dashboard Name API from Akkio — 1 operation(s) for dashboard name.
- [Akkio Data Sources API](https://apis.io/apis/akkio/akkio-data-sources-api/) — The Data Sources API from Akkio — 5 operation(s) for data sources.
- [Akkio Dataset Snapshot API](https://apis.io/apis/akkio/akkio-dataset-snapshot-api/) — The Dataset Snapshot API from Akkio — 1 operation(s) for dataset snapshot.
- [Akkio Dataset Updates API](https://apis.io/apis/akkio/akkio-dataset-updates-api/) — The Dataset Updates API from Akkio — 1 operation(s) for dataset updates.
- [Akkio Distribution API](https://apis.io/apis/akkio/akkio-distribution-api/) — The distribution API from Akkio — 3 operation(s) for distribution.
- [Akkio Entertainment Suite API](https://apis.io/apis/akkio/akkio-entertainment-suite-api/) — The Entertainment Suite API from Akkio — 5 operation(s) for entertainment suite.
- [Akkio Event Handler API](https://apis.io/apis/akkio/akkio-event-handler-api/) — The Event Handler API from Akkio — 1 operation(s) for event handler.
- [Akkio Fast API](https://apis.io/apis/akkio/akkio-fastapi-api/) — The FastAPI API from Akkio — 3 operation(s) for fastapi.
- [Akkio Forecast Preview API](https://apis.io/apis/akkio/akkio-forecast-preview-api/) — The Forecast Preview API from Akkio — 1 operation(s) for forecast preview.
- [Akkio Generate Document Upload Url API](https://apis.io/apis/akkio/akkio-generate-document-upload-url-api/) — The Generate Document Upload Url API from Akkio — 1 operation(s) for generate document upload url.
- [Akkio Generate Download Url API](https://apis.io/apis/akkio/akkio-generate-download-url-api/) — The Generate Download Url API from Akkio — 1 operation(s) for generate download url.
- [Akkio Generate Download Url With Dataset Id API](https://apis.io/apis/akkio/akkio-generate-download-url-with-dataset-id-api/) — The Generate Download Url With Dataset Id API from Akkio — 1 operation(s) for generate download url with dataset id.
- [Akkio Generate Upload Dataset Url API](https://apis.io/apis/akkio/akkio-generate-upload-dataset-url-api/) — The Generate Upload Dataset Url API from Akkio — 1 operation(s) for generate upload dataset url.
- [Akkio Generate Upload Url API](https://apis.io/apis/akkio/akkio-generate-upload-url-api/) — The Generate Upload Url API from Akkio — 1 operation(s) for generate upload url.
- [Akkio Generative Dashboard API](https://apis.io/apis/akkio/akkio-generative-dashboard-api/) — The Generative Dashboard API from Akkio — 3 operation(s) for generative dashboard.
- [Akkio Get Cleaning Ops API](https://apis.io/apis/akkio/akkio-get-cleaning-ops-api/) — The Get Cleaning Ops API from Akkio — 1 operation(s) for get cleaning ops.
- [Akkio Group Forecast API](https://apis.io/apis/akkio/akkio-group-forecast-api/) — The Group Forecast API from Akkio — 1 operation(s) for group forecast.
- [Akkio Health API](https://apis.io/apis/akkio/akkio-health-api/) — The Health API from Akkio — 1 operation(s) for health.
- [Akkio Health Check API](https://apis.io/apis/akkio/akkio-health-check-api/) — The Health Check API from Akkio — 1 operation(s) for health check.
- [Akkio Hubspot Contacts API](https://apis.io/apis/akkio/akkio-hubspot-contacts-api/) — The Hubspot Contacts API from Akkio — 1 operation(s) for hubspot contacts.
- [Akkio Images API](https://apis.io/apis/akkio/akkio-images-api/) — The Images API from Akkio — 4 operation(s) for images.
- [Akkio Inference API](https://apis.io/apis/akkio/akkio-inference-api/) — The Inference API from Akkio — 1 operation(s) for inference.
- [Akkio Inference Status API](https://apis.io/apis/akkio/akkio-inference-status-api/) — The Inference Status API from Akkio — 1 operation(s) for inference status.
- [Akkio Insight API](https://apis.io/apis/akkio/akkio-insight-api/) — The insight API from Akkio — 1 operation(s) for insight.
- [Akkio Integrations API](https://apis.io/apis/akkio/akkio-integrations-api/) — The Integrations API from Akkio — 35 operation(s) for integrations.
- [Akkio Knowledge API](https://apis.io/apis/akkio/akkio-knowledge-api/) — The knowledge API from Akkio — 3 operation(s) for knowledge.
- [Akkio List Categorical Field Values API](https://apis.io/apis/akkio/akkio-list-categorical-field-values-api/) — The List Categorical Field Values API from Akkio — 1 operation(s) for list categorical field values.
- [Akkio List Flow Fields API](https://apis.io/apis/akkio/akkio-list-flow-fields-api/) — The List Flow Fields API from Akkio — 1 operation(s) for list flow fields.
- [Akkio List Zapier Flows API](https://apis.io/apis/akkio/akkio-list-zapier-flows-api/) — The List Zapier Flows API from Akkio — 1 operation(s) for list zapier flows.
- [Akkio Llm Meltano Helper API](https://apis.io/apis/akkio/akkio-llm-meltano-helper-api/) — The llm_meltano_helper API from Akkio — 1 operation(s) for llm_meltano_helper.
- [Akkio Llm Summarizer API](https://apis.io/apis/akkio/akkio-llm-summarizer-api/) — The Llm Summarizer API from Akkio — 1 operation(s) for llm summarizer.
- [Akkio Location Intelligence API](https://apis.io/apis/akkio/akkio-location-intelligence-api/) — The Location Intelligence API from Akkio — 5 operation(s) for location intelligence.
- [Akkio Measurement API](https://apis.io/apis/akkio/akkio-measurement-api/) — The measurement API from Akkio — 10 operation(s) for measurement.
- [Akkio Merge API](https://apis.io/apis/akkio/akkio-merge-api/) — The Merge API from Akkio — 1 operation(s) for merge.
- [Akkio Merge Status API](https://apis.io/apis/akkio/akkio-merge-status-api/) — The Merge Status API from Akkio — 1 operation(s) for merge status.
- [Akkio Metrics API](https://apis.io/apis/akkio/akkio-metrics-api/) — The metrics API from Akkio — 1 operation(s) for metrics.
- [Akkio Modeling API](https://apis.io/apis/akkio/akkio-modeling-api/) — The modeling API from Akkio — 12 operation(s) for modeling.
- [Akkio Nonce API](https://apis.io/apis/akkio/akkio-nonce-api/) — The Nonce API from Akkio — 1 operation(s) for nonce.
- [Akkio Parse API](https://apis.io/apis/akkio/akkio-parse-api/) — The Parse API from Akkio — 1 operation(s) for parse.
- [Akkio Platform One API](https://apis.io/apis/akkio/akkio-platform-one-api/) — The platform-one API from Akkio — 2 operation(s) for platform-one.
- [Akkio Projects API](https://apis.io/apis/akkio/akkio-projects-api/) — The Projects API from Akkio — 2 operation(s) for projects.
- [Akkio Proof of Concept API](https://apis.io/apis/akkio/akkio-proof-of-concept-api/) — The Proof of Concept API from Akkio — 15 operation(s) for proof of concept.
- [Akkio Refresh API](https://apis.io/apis/akkio/akkio-refresh-api/) — The Refresh API from Akkio — 1 operation(s) for refresh.
- [Akkio Refresh Live Flow Dataset API](https://apis.io/apis/akkio/akkio-refresh-live-flow-dataset-api/) — The Refresh Live Flow Dataset API from Akkio — 4 operation(s) for refresh live flow dataset.
- [Akkio Rfm API](https://apis.io/apis/akkio/akkio-rfm-api/) — The Rfm API from Akkio — 6 operation(s) for rfm.
- [Akkio RFM UPC Processing API](https://apis.io/apis/akkio/akkio-rfm-upc-processing-api/) — The RFM UPC Processing API from Akkio — 4 operation(s) for rfm upc processing.
- [Akkio Segment API](https://apis.io/apis/akkio/akkio-segment-api/) — The segment API from Akkio — 3 operation(s) for segment.
- [Akkio Shopify API](https://apis.io/apis/akkio/akkio-shopify-api/) — The Shopify API from Akkio — 3 operation(s) for shopify.
- [Akkio Slack App API](https://apis.io/apis/akkio/akkio-slack-app-api/) — The Slack App API from Akkio — 5 operation(s) for slack app.
- [Akkio Snapshot API](https://apis.io/apis/akkio/akkio-snapshot-api/) — The Snapshot API from Akkio — 1 operation(s) for snapshot.
- [Akkio Stats API](https://apis.io/apis/akkio/akkio-stats-api/) — The Stats API from Akkio — 3 operation(s) for stats.
- [Akkio Status API](https://apis.io/apis/akkio/akkio-status-api/) — The Status API from Akkio — 1 operation(s) for status.
- [Akkio Synthetics API](https://apis.io/apis/akkio/akkio-synthetics-api/) — The Synthetics API from Akkio — 6 operation(s) for synthetics.
- [Akkio Train API](https://apis.io/apis/akkio/akkio-train-api/) — The Train API from Akkio — 1 operation(s) for train.
- [Akkio Training API](https://apis.io/apis/akkio/akkio-training-api/) — The Training API from Akkio — 3 operation(s) for training.
- [Akkio Transforms API](https://apis.io/apis/akkio/akkio-transforms-api/) — The Transforms API from Akkio — 4 operation(s) for transforms.
- [Akkio Transforms (SQL) API](https://apis.io/apis/akkio/akkio-transforms-sql-api/) — The Transforms (SQL) API from Akkio — 2 operation(s) for transforms (sql).
- [Akkio Version API](https://apis.io/apis/akkio/akkio-version-api/) — The Version API from Akkio — 1 operation(s) for version.
- [Akkio Webhook API](https://apis.io/apis/akkio/akkio-webhook-api/) — The Webhook API from Akkio — 3 operation(s) for webhook.
- [Akkio Zapier API](https://apis.io/apis/akkio/akkio-zapier-api-api/) — The Zapier Api API from Akkio — 1 operation(s) for zapier api.
- [Akkio O Auth API](https://apis.io/apis/akkio/akkio-oauth-api/) — The OAuth API from Akkio — 3 operation(s) for oauth.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [akkio](https://apis.io/servers/akkio/akkio/)

#### Collections (2)

Postman and Open Collection request collections.

- [Akkio Datasets API](https://apis.io/collections/akkio/open-akkio-datasets-api/)
- [Akkio Datasets Models API](https://apis.io/collections/akkio/open-akkio-models-api/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Akkio Legacy V1 Overlay](https://apis.io/overlays/akkio/akkio-legacy-v1-overlay/)
- [Akkio Public Api Overlay](https://apis.io/overlays/akkio/akkio-public-api-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Akkio Authentication](https://apis.io/security/akkio/akkio-authentication/)
- [Akkio Domain Security](https://apis.io/security/akkio/akkio-domain-security/)
- [Akkio Trust Center](https://apis.io/security/akkio/akkio-trust-center/)
- [Akkio Vulnerability Disclosure](https://apis.io/security/akkio/akkio-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Akkio Plans Pricing](https://apis.io/plans/akkio/akkio-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Akkio Rate Limits](https://apis.io/rate-limits/akkio/akkio-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.akkio.com/)
- [Documentation](https://docs.akkio.com/akkio-docs)
- [Getting started](https://docs.akkio.com/akkio-docs/rest-api/api-introduction/quickstart)
- [API reference](https://docs.akkio.com/akkio-docs/endpoints-and-schemas/endpoints)
- [Pricing](https://www.akkio.com/pricing)
- [Sign up](https://app.akkio.com/)
- [Support](https://docs.akkio.com/akkio-help-center)
- [Blog](https://www.akkio.com/blog)
- [Security](https://www.akkio.com/security)
- [Compliance](https://www.akkio.com/security)
- [Terms of service](https://www.akkio.com/terms)
- [Privacy policy](https://www.akkio.com/privacy)
- [GitHub](https://github.com/akkio-inc)

## API Evangelist rating

**Kin Score 49.2** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 40.5 |
| Contract governance | 18.2 |
| Operational transparency | 34.2 |
| Developer ergonomics | 66.1 |
| Access clarity | 47.4 |

**Agent readiness 23.3** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | — |

**Regulatory alignment 32.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/akkio/](https://apis.io/providers/akkio/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Akkio: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/akkio/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
