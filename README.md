# CarVinsight buffer-assets

Public image host for scheduled Facebook and LinkedIn posts (Buffer).

## Use jsDelivr, not raw

Buffer needs a public HTTPS URL that returns the image bytes with an `image/*` content type.

- Correct: `https://cdn.jsdelivr.net/gh/carvinsight-kft/buffer-assets@main/<path>` — measured `content-type: image/png`
- Wrong: `https://raw.githubusercontent.com/...` — measured `content-type: application/octet-stream`, which Buffer rejects
- Also wrong: Google Drive and Dropbox share links

The earlier instruction in this file (raw URLs returning `image/jpeg`) was incorrect and has been corrected.

## Naming

`<YYYY>/<YYYY-MM-DD>-<facebook|linkedin>-<slug>.png`

ASCII-only slug. Facebook and LinkedIn need different images for the same post, so never share one path between the two channels.

## Caching

Branch URLs are edge-cached for about 12 hours. Never overwrite a published path — publish a new filename instead. If a path really must be replaced, purge it via `purge.jsdelivr.net`.

## Scope

Everything in this repository is public and browsable. Only publish assets that are fine to be public. No customer data, no internal screenshots, no drafts.
