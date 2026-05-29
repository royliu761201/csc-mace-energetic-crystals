# CL-20/HMX Target Data Provenance Note

This note consolidates the current target-data provenance story into one reviewer-facing artifact. It is designed to answer three distinct questions cleanly:

1. What is the canonical benchmark file used in the manuscript?
2. What upstream package-level evidence can be verified locally?
3. Which provenance and thermodynamic details remain incomplete?

## Canonical benchmark file

- canonical staged target file:
  - `data/raw/cl20_hmx_target_subset_v1.extxyz`
- canonical conversion script:
  - `scripts/prepare_cl20_hmx_target_from_deepmd.py`
- canonical source tag in the staged release:
  - `cl20_hmx_target_v1`
- staged regime label:
  - `decomposition`

The staged file preserves:

- periodic cell vectors
- atomic coordinates
- total energies
- per-atom forces
- material identity
- DeepMD shard identity
- synthesized frame-level `trajectory_id`

## Current benchmark composition

- total labeled frames: `14814`
- material balance:
  - `CL-20 = 4875`
  - `HMX = 9939`
- atom counts:
  - `CL-20 = 288 atoms/frame`
  - `HMX = 56 atoms/frame`
- current split:
  - deterministic contiguous frame-index split `11851 / 1481 / 1482`

## Provider-confirmed sampling summary

Provider feedback now clarifies the staged subset beyond the package names alone:

- both `HMX` and `CL-20` were sampled at scale factors:
  - `0.96`
  - `1.00`
  - `1.04`
- for each scale point, configurations were retained at:
  - `300 K`
  - `500 K`
  - `1000 K`
  - `2000 K`
  - `3000 K`
  - `4000 K`
- configurations with cell edge length `< 10 Å` were removed before final assembly
- final retained counts after that filtering step:
  - `HMX = 9939`
  - `CL-20 = 4875`

The provider identified the corresponding sampling reference as:

- Wen et al., *Phys. Chem. Chem. Phys.* **2024**, 26, 9984--9997

## Recovered upstream package-level provenance

The current workspace snapshot contains enough local evidence to identify the package-level DeepMD roots from which the staged subset was assembled.

### CL-20 package

- upstream package name:
  - `1-CL-20-Total`
- inspected root:
  - `.tmp_dongping_inspect/1-CL-20-Total/1-CL-20-Total`
- recovered DeepMD shards:
  - `set.000`
- recovered frame count:
  - `4875`
- atom types:
  - `C, H, N, O`
- extra package files present:
  - `idx.txt`
  - `tag.txt`
  - `test.xyz`

### HMX package

- upstream package name:
  - `2-HMX-trainset3`
- inspected root:
  - `.tmp_dongping_inspect/2-HMX-trainset3/2-HMX-trainset3`
- recovered DeepMD shards:
  - `set.000`
  - `set.001`
- recovered frame counts:
  - `5000`
  - `4939`
- total recovered HMX frames:
  - `9939`
- atom types:
  - `C, H, N, O`

### What this package-level recovery now establishes

- the final target is not an ad hoc extxyz-only subset
- the staged benchmark can be traced back to two named upstream DeepMD packages
- the package-level frame counts match the canonical staged subset exactly
- the conversion path from DeepMD arrays to the canonical extxyz is locally verifiable

## What the current release supports

The current CL-20/HMX release supports:

- a real energetic-material static benchmark on labeled CL-20/HMX configurations
- rollout-to-structure comparisons using force-labeled periodic frames
- material-aware interpretation at the combined-target level
- explicit statement of frame-dominated nonequilibrium failure boundaries

## What the current release does not yet support

The current CL-20/HMX release does not yet support reviewer-proof claims about:

- exchange-correlation functional
- dispersion treatment
- cutoff / basis / k-point settings
- exact upstream labeling workflow
- shock/compression generation route before labeling
- per-frame pressure histories
- per-frame temperature histories
- reusable trajectory grouping for leakage-aware splitting

## External methodological anchor

The current workspace now also has a public-method anchor for the likely DFT lineage of `HMX` and `CL-20`, documented in:

- `results/target/cl20_hmx_external_method_anchor_note.md`

That external anchor points to publicly available papers from the same energetic-material modeling group and the same corresponding author (`Dongping Chen`) reporting:

- `CP2K`
- `PBE-D3`
- `DZVP-MOLOPT`
- `60/400 Ry` cutoffs
- `300–4000 K` AIMD sampling
- `DP-GEN` augmentation

for foundational `HMX` / `CL-20` neural-network-potential datasets. The new provider clarification is materially stronger than the earlier external-only anchor because it explicitly confirms the subset-level scale factors, temperature grid, and `< 10 Å` cell-edge filtering step for the present staged release. However, because the current workspace still does not retain a direct machine-readable metadata file or full upstream labeling record, we still treat the exact electronic-structure setup and shock/compression workflow as incomplete provenance rather than as fully reproduced metadata.

## Interpretation boundary

The practical interpretation boundary is therefore:

- supported now:
  - static ranking on real CL-20/HMX configurations
  - nonequilibrium rollout comparison on real CL-20/HMX configurations
  - active-versus-inert charge-response analysis
  - frame-dominated failure-boundary analysis
- not supported yet:
  - pressure-resolved mechanism claims
  - temperature-resolved mechanism claims
  - trajectory-history-resolved leakage-prevention claims
  - reviewer-complete upstream DFT reproducibility claims

## Recommended reviewer-proof wording

> The current CL-20/HMX target subset was staged from two named upstream DeepMD-format packages recovered in the local workspace snapshot: `1-CL-20-Total` for CL-20 and `2-HMX-trainset3` for HMX. Provider clarification further indicates that the staged subset samples scale factors `0.96`, `1.00`, and `1.04`, retains configurations at `300`, `500`, `1000`, `2000`, `3000`, and `4000 K` for each scale point, and excludes configurations with cell edge lengths below `10 Å`, consistent with the sampling strategy reported by Wen et al. (*Phys. Chem. Chem. Phys.* 2024, 26, 9984--9997). The conversion path to the canonical extxyz benchmark preserves periodic cell, coordinates, total energy, per-atom forces, material identity, and DeepMD shard identity, and the recovered package-level frame counts match the staged subset exactly. However, the present snapshot still does not retain a reviewer-complete record of the upstream electronic-structure labeling settings, per-frame thermodynamic metadata, or the shock/compression generation workflow, so those details remain explicit limits of the current release rather than claims of the manuscript.
