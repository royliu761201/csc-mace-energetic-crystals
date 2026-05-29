# CL-20/HMX Target Split Upgrade Note

This note records the first concrete step toward a cleaner CL-20/HMX target evaluation protocol.

## Why this note exists

The manuscript correctly states that the original target split was a deterministic contiguous frame-index split. Because the staged target file was written as all `CL-20` frames followed by all `HMX` frames, that design produced an `HMX`-only held-out test segment.

That limitation remains an important reviewer-facing boundary for the published results. However, the repository now also contains a concrete target-specific metadata and split upgrade path.

## New target-specific metadata bundle

A new script now builds a CL-20/HMX-specific manifest and split summary directly from the canonical target file:

- script:
  - `scripts/build_cl20_hmx_target_metadata_bundle.py`
- default output directory:
  - `data/metadata/cl20_hmx_target_v1`

The generated bundle includes:

- `dataset_manifest.csv`
- `split_summary.json`
- `cl20_hmx_target_metadata_summary.json`
- `cl20_hmx_target_metadata_summary.md`

## What the first upgraded split already fixes

With `--stratify-fields material`, the new split is no longer `HMX`-only on held-out evaluation.

Current counts from the generated summary:

- `train`
  - `CL-20 = 3900`
  - `HMX = 7951`
- `val`
  - `CL-20 = 487`
  - `HMX = 993`
- `test`
  - `CL-20 = 488`
  - `HMX = 995`

This is already a materially cleaner target split than the manuscript's original contiguous split because the held-out slice now contains **both materials**.

## What this upgraded split still does not solve

This is a real improvement, but not a complete provenance solution.

The current upgraded split is still:

- frame-level rather than trajectory-level;
- based on the metadata already present in the staged target file; and
- not yet temperature-stratified in reviewer-proof form.

The current staged `extxyz` still does not preserve explicit per-frame temperature and pressure fields, and its `trajectory_id` remains effectively frame-unique. So this split upgrade should be described as:

`a cleaner material-balanced held-out protocol, not a final trajectory-aware or temperature-aware target split.`

## Why this still matters

Even with those remaining limits, this split upgrade is a meaningful positive step because it reduces the strongest benchmark-purity objection without requiring a training-stack rewrite. It also creates a concrete path for the next static evaluation:

1. build target-specific metadata;
2. point the CL-20/HMX evaluation to that metadata;
3. repeat the smallest possible held-out static comparison under the upgraded split.

That is the shortest route from the current manuscript boundary

`contiguous split with HMX-only test`

to a more defensible target claim

`material-balanced held-out CL-20/HMX evaluation`.
