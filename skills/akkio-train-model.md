---
name: Train an Akkio predictive model
description: Create a dataset, load rows, and train a model that predicts a target column.
api: openapi/akkio-api-openapi.yml
operations: [postDataset, getDatasets, postModel]
---

# Train an Akkio predictive model

Use the Akkio API (`https://api.akk.io/v1`) to build a model that predicts a target column from tabular data.

## Auth
Every request carries your Akkio API key (issue one at https://app.akk.io/team-settings). On `GET` send it as the `api_key` query parameter; on `POST`/`DELETE` send it as the `api_key` field in the JSON body.

## Steps
1. **Create a dataset** — `postDataset` (`POST /datasets`) with `{ "api_key": "...", "name": "my dataset" }`. Capture `dataset_id` from the response.
2. **Load rows** — `postDataset` (`POST /datasets`) with `{ "api_key": "...", "id": "<dataset_id>", "rows": [ {...}, ... ] }`. Each row is an object of column→value.
3. **(Optional) confirm** — `getDatasets` (`GET /datasets?api_key=...`) to verify the dataset is present.
4. **Train** — `postModel` (`POST /models`) with `{ "api_key": "...", "dataset_id": "<dataset_id>", "predict_fields": ["<target>"], "ignore_fields": [], "duration": 10 }`. `duration` is the training budget in minutes. Capture `model_id`.

## Notes
- `POST /datasets` and `POST /models` are overloaded by body shape — include exactly the fields for the action you want.
- No idempotency key is supported; avoid blind retries on `POST`.
