---
name: Train an Akkio model with the async Training API
description: Submit a training job on the current /api/v1 Training API, poll the task to completion, and fetch the model — the supported replacement for the legacy /v1/models train call.
api: openapi/_original/akkio-public-api-openapi.yaml
operations:
  - _submit_controller_api_v1_models_train_new_post
  - _get_status_controller_api_v1_models_train__task_id__status_get
  - _get_result_controller_api_v1_models_train__task_id__result_get
---

# Train an Akkio model with the async Training API

Akkio's current training surface is `POST /api/v1/models/train/new` on `https://api.akkio.com`. Akkio's own docs describe it as "a better-designed v2 of our legacy `/v1/models` route" — prefer it over the legacy call. Every operationId below is verbatim from the spec Akkio serves at `https://api.akkio.com/api/v1/api.yaml`.

## Auth

Send `X-API-Key: <your key>` as a **header** on every call. Issue and rotate keys at https://app.akkio.com/team-settings. The key is team/organization scoped and has no scopes — it grants everything the organization can reach.

- `401` means the key is missing, wrong, or has leading/trailing whitespace. Trim it.
- `403` means the key's organization does not have access to that dataset or project.

You need a dataset first. Upload one in the app, import it through an integration, or create it with the legacy `postDataset` call (`POST /v1/datasets`) — the legacy datasets route is still the only programmatic way to create one.

## Steps

1. **Submit the job** — `_submit_controller_api_v1_models_train_new_post` (`POST /api/v1/models/train/new`). Body is `TrainRequestPayload`:

   ```json
   {
     "dataset_id": "YTV32jCdVf5DbcMxzvX5",
     "predict_fields": ["Positive Lead"],
     "duration": 60,
     "ignore_fields": [],
     "extra_attention": false,
     "force": false
   }
   ```

   - `dataset_id`, `predict_fields` and `duration` are **required**.
   - `duration` is an enum, not free-form: `10` (Fastest), `60` (High Quality), `300` (Higher Quality), `1800` (Production).
   - `predict_fields` and `ignore_fields` are **case sensitive** — they must match the dataset's column names exactly.
   - `extra_attention: true` helps when the target class is rare.
   - `force: true` creates a new model even if one already exists. Leave it `false` unless you mean it.

   A `201` returns `APITaskStartedResponse`: `{"task_id": "..."}`. Capture it.

2. **Poll the task** — `_get_status_controller_api_v1_models_train__task_id__status_get` (`GET /api/v1/models/train/{task_id}/status`). Returns `APIStatusResponse`:

   ```json
   { "status": "IN_PROGRESS", "metadata": { "type": "IN_PROGRESS", "estimate_seconds": 45 } }
   ```

   `status` is one of `PENDING`, `IN_PROGRESS`, `SUCCEEDED`, `FAILED`, `UNKNOWN_TIMEOUT`. `metadata` is a discriminated union on `type`:
   - `IN_PROGRESS` may carry `estimate_seconds` — documented as a rough best-effort estimate, not a guarantee. Do not treat it as a deadline.
   - `SUCCEEDED` carries `location`, the path to GET the result from.
   - `FAILED` carries `error`, a human-readable reason.

3. **Fetch the result** — `_get_result_controller_api_v1_models_train__task_id__result_get` (`GET /api/v1/models/train/{task_id}/result`), once and only once status is `SUCCEEDED`.

## Rules that will bite you

- **A failed job returns HTTP 200.** The status poll answers `200` with `"status": "FAILED"` in the body. If you branch on HTTP status alone you will read a failed training run as a success. Always read the `status` field.
- **There is no idempotency key.** Akkio documents none, and neither published spec declares one. If a submit times out, you cannot safely retry — a second call starts a second training job. Record the `task_id` before doing anything else, and on an ambiguous submit prefer listing models over re-submitting.
- **Budget your polling.** The published throughput limit is five requests per second across the whole API (FAQ), with no rate-limit response headers and no documented `429`. Back off on an interval measured in seconds, not milliseconds, and scale it with the `duration` you asked for — a `1800` job does not need sub-minute polling.
- **`422` is the only declared error.** It returns `HTTPValidationError`: `{"detail": [{"loc": [...], "msg": "...", "type": "..."}]}`. `loc` names the offending field path — surface it rather than the raw blob. `401`, `403` and `404` are real but are documented only in prose and are absent from the spec, so a generated client will not model them.
- **The SDKs will not help here.** PyPI `akkio` and npm `akkio` are both 1.0.5 from 2021-03-05 and cover only the legacy `/v1` surface. For `/api/v1`, generate a client from `https://api.akkio.com/api/v1/api.yaml` — Akkio documents that path explicitly.

## See also

- `conventions/akkio-conventions.yml` — the submit/poll/fetch contract in full
- `errors/akkio-problem-types.yml` — both error envelopes and the in-band FAILED metadata
- `skills/akkio-chat-explore.md` — asking questions of the data instead of training on it
