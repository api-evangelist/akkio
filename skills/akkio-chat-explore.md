---
name: Ask questions of Akkio data with Chat Explore
description: Configure a project's custom instructions, submit a natural-language question against a project or dataset, poll the task, and read back the answer with its charts and tables.
api: openapi/_original/akkio-public-api-openapi.yaml
operations:
  - _create_new_project_api_v1_projects_post
  - _update_project_api_v1_projects__project_id__put
  - _get_project_api_v1_projects__project_id__get
  - _submit_chat_explore_query_api_v1_chat_explore_new_post
  - _get_chat_explore_status_api_v1_chat_explore_status__task_id__get
  - _get_chat_api_v1_chat_explore_chats__id__get
---

# Ask questions of Akkio data with Chat Explore

Chat Explore is Akkio's "chat with your data" assistant, and its API is the single most useful Akkio surface for an agent: you hand it a project or dataset and a question in natural language, and it answers with prose, charts and tables. Base host `https://api.akkio.com`. Every operationId below is verbatim from `https://api.akkio.com/api/v1/api.yaml`.

## Auth

`X-API-Key: <your key>` header on every call. Keys come from https://app.akkio.com/team-settings and are organization-scoped with no scopes.

## Step 0 — decide: project or dataset

Chat Explore accepts either a `project_id` or a `dataset_id`. **This choice is not cosmetic.** Custom instructions attached to a project are only applied when you call with `project_id`. If you call with `dataset_id`, your `chatContext` / `chatInstructions` / `chatSuggestions` are silently ignored. If you have steering configuration, always call with `project_id`.

## Step 1 — set up the project's steering fields

- Create: `_create_new_project_api_v1_projects_post` (`POST /api/v1/projects`).
- Read: `_get_project_api_v1_projects__project_id__get` (`GET /api/v1/projects/{project_id}`) returns `GetProjectResponse`.
- Update: `_update_project_api_v1_projects__project_id__put` (`PUT /api/v1/projects/{project_id}`).
- Delete: `_delete_project_api_v1_projects__project_id__delete` (`DELETE /api/v1/projects/{project_id}`).

Three free-text fields steer every answer, and they are the highest-leverage thing you control:

| Field | What it is for | Akkio's own examples |
|---|---|---|
| `chatContext` | What Chat Explore should know about your application | "This dataset is customer engagement data"; "The units of the sales column are in millions" |
| `chatInstructions` | How it should respond | "Respond only in Spanish"; "Provide short and concise answers only" |
| `chatSuggestions` | Newline-separated starter questions the UI offers | "What is the average net media cost by campaign ID?" |

`GetProjectResponse` requires only `id`; `name` (the schema calls it "the name of the flow") and the three chat fields all default to empty strings.

## Step 2 — submit the question

`_submit_chat_explore_query_api_v1_chat_explore_new_post` (`POST /api/v1/chat-explore/new`), passing the project (or dataset) and your question. Returns `201` with `{"task_id": "..."}`.

## Step 3 — poll

`_get_chat_explore_status_api_v1_chat_explore_status__task_id__get` (`GET /api/v1/chat-explore/status/{task_id}`) until `status` is `SUCCEEDED`. Same `APIStatusResponse` shape as training: `PENDING`, `IN_PROGRESS` (optional `estimate_seconds`), `SUCCEEDED` (with `location`), `FAILED` (with `error`).

## Step 4 — read the conversation

`_get_chat_api_v1_chat_explore_chats__id__get` (`GET /api/v1/chat-explore/chats/{id}`). Messages are `APIChatMessage`:

- `role` — `user` or `assistant` (required)
- `content` — the text (required)
- `images` — an array, possibly empty. Entries are **base64 image strings or stringified Plotly JSON**. Akkio documents the images as currently PNG but explicitly reserves the right to change that: assume base64, do not assume PNG.
- `table` — either `null` or a list of row objects keyed by column name. Values are any JSON-serializable type, **not necessarily strings** — do not assume string and parse.

## Rules that will bite you

- **A failed query returns HTTP 200** with `"status": "FAILED"` in the body. Read the field, not the status line.
- **Chat Explore is documented as stateless** — conversation context is supplied per call, not held server-side. Carry your own history.
- **Five requests per second** across the whole API, no rate-limit headers, no documented `429`. Poll on a seconds-scale interval.
- **`422` is the only declared error** (`HTTPValidationError`, with `detail[].loc` naming the bad field). `401` (bad or whitespace-padded key) and `403` (organization lacks access) are documented in prose only.
- **No idempotency key.** A retried submit is a second question, billed and executed as such.

## See also

- `conventions/akkio-conventions.yml` — submit/poll/fetch, statelessness, image and table encodings
- `data-model/akkio-data-model.yml` — Project, Chat, ChatMessage and Task shapes
- `errors/akkio-problem-types.yml` — error envelopes
