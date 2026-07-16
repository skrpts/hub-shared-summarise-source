# Release Notes

## v1.0.4
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.0.3
GH#749 — make the prompt position-safe (§4.3.1). Replace the hardcoded positional ref `{{steps.Literature Search.output}}` (a dangling reference for any consumer without a "Literature Search" step — flagged `execution_step_ref_unresolved` by the canonical scan) with `{{step.context.source_text}}`. Consumers now supply the source via a `bindings: source_text` (step-sourced) — Phase 1 wires literature-review-pipeline + systematic-review-pipeline; input-sourced consumers wait on the `from_input` engine binding (#750).

## v1.0.2
GH#657 Framing B — republish wave. Bundle now ships `dependencies: []` in its signed manifest (injected by `publish-skrpt.mjs` for `--shared` publishes), so the App's dep-referenced install pipeline (post-PR #47) accepts it on standalone update via Hub Update-all. No content changes.

## v1.0.1
GH#645 Row 3a — republish with `manifest.id` aligned to Hub catalog UUID. Pre-K-037 v1.0.0 bundle carried a local `manifest.id` that drifted from the catalog UUID. Row 5 (`0d9c9dbe`) reconciled the source file but not the signed bundle; v1.0.1 ships the corrected `manifest.id` so the batch-of-81 consumer migrations (GH#645 Row 3b) can pin this version and pass engine STEP 4d. No content changes.

## v1.0.0
Initial catalog release as independent shared object (GH#625 Step 2; canonical pick + rename surface per audit).
