# CL-20/HMX Labeling Provenance Note

## What is currently established from the repository

- The canonical final-target file is:
  - `data/raw/cl20_hmx_target_subset_v1.extxyz`
- This file was generated from DeepMD-format labeled data through:
  - `scripts/prepare_cl20_hmx_target_from_deepmd.py`
- The conversion script states that the source data are:
  - "CL-20/HMX DeepMD-format labeled data staged within the collaboration"
- The conversion pipeline expects two extracted dataset roots:
  - one `CL-20` root
  - one `HMX` root
- For each root, the script reads:
  - `type_map.raw`
  - `type.raw`
  - `set.* / coord.npy`
  - `set.* / force.npy`
  - `set.* / energy.npy`
  - `set.* / box.npy`
- During conversion, the script materializes:
  - periodic cells
  - atomic coordinates
  - total energies
  - per-atom forces
  - `material`
  - `deepmd_set`
  - `trajectory_id`
  - `regime`
  - `source_tag`

## What the staged extxyz currently preserves

- `source_tag = cl20_hmx_target_v1`
- `material = cl20` or `hmx`
- `regime = decomposition`
- `deepmd_set = set.000` or `set.001`
- `pressure_gpa = unknown`
- `temperature_k = unknown`

## What we can support in the manuscript right now

- The final target is not a synthetic placeholder; it is derived from real labeled CL-20/HMX structures converted from DeepMD-format arrays.
- The current release preserves real energies and forces, plus material identity and DeepMD shard identity.
- The current release does not preserve reviewer-proof electronic-structure provenance such as:
  - exchange-correlation functional
  - dispersion treatment
  - basis / cutoff / k-point settings
  - labeling workflow
  - shock-state generation route before labeling

## What still needs to be recovered before submission

- Original collaboration note or README for the CL-20 DeepMD root
- Original collaboration note or README for the HMX DeepMD root
- DFT labeling settings
- Sampling / generation route for decomposition configurations
- Any mapping from `set.000` / `set.001` to thermodynamic or trajectory batches

## Recommended manuscript wording

Use language no stronger than:

> The current CL-20/HMX final-target subset was staged from collaboration-held DeepMD-format labeled data and converted into a canonical extxyz representation preserving cell, coordinates, total energy, per-atom forces, material identity, and DeepMD shard identity. However, the present repository snapshot does not yet retain a reviewer-complete record of the upstream electronic-structure labeling settings or trajectory-generation workflow, so those details remain an explicit target for the next data release rather than a claim of the current manuscript.
