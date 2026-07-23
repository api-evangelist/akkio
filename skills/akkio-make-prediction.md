---
name: Make predictions with an Akkio model
description: List trained models and score new records against one, optionally with explanations.
api: openapi/akkio-api-openapi.yml
operations: [getModels, postModel]
---

# Make predictions with an Akkio model

Score new records against an already-trained Akkio model via the Akkio API (`https://api.akk.io/v1`).

## Auth
Send your Akkio API key as the `api_key` query parameter on `GET` and as the `api_key` JSON body field on `POST`. Issue keys at https://app.akk.io/team-settings.

## Steps
1. **Find your model** — `getModels` (`GET /models?api_key=...`). Pick the `model_id` you want to predict with.
2. **Predict** — `postModel` (`POST /models`) with `{ "api_key": "...", "id": "<model_id>", "data": [ {...}, ... ], "explain": false }`. Each object in `data` is a record with the model's input columns.
3. **(Optional) explanations** — set `"explain": true` to receive per-feature attribution for each prediction.

## Notes
- The same `POST /models` endpoint trains when given `dataset_id` + `predict_fields`, and predicts when given `id` + `data` — send the prediction fields only.
- Responses are plain JSON; there is no RFC 9457 problem+json error contract.
