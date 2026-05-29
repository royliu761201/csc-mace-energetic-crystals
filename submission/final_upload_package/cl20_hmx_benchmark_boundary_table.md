# CL-20/HMX Benchmark Boundary

This table is meant to answer the reviewer question directly: what does the current CL-20/HMX release support, and what remains out of scope?

- Total labeled frames: `14814`
- Material balance: `CL-20=4875`, `HMX=9939`
- Current split: `11851/1481/1482` contiguous frame-index partition
- Provider-confirmed subset sampling:
  - scale factors `0.96 / 1.00 / 1.04`
  - temperatures `300 / 500 / 1000 / 2000 / 3000 / 4000 K`
  - configurations with cell edge `< 10 Å` removed
  - source arrays written in fixed `scale -> temperature` order, enabling post-conversion mapping back to concrete temperature/scale conditions
  - sampling lineage consistent with Wen et al., *Phys. Chem. Chem. Phys.* **2024**, 26, 9984--9997

| Component | Current status | Evidence | Claim supported now | Claim not supported yet |
| --- | --- | --- | --- | --- |
| Force labels | available | All `14814` frames carry energy/force labels in the staged subset. | Static ranking and rollout-to-structure comparisons. | None on this axis. |
| Material identity | available | Subset contains `4875` CL-20 frames and `9939` HMX frames. | Combined energetic-material benchmark. | Regenerated material-split static error table from the current local checkout. |
| Sampling grid | available_with_boundary | Provider-confirmed scales `0.96/1.00/1.04`, temperatures `300–4000 K`, fixed write order by `scale -> temperature`, and `<10 Å` cell-edge filtering. | A real energetic-material sampling ladder with recoverable temperature/scale assignment for the staged subset. | Per-frame thermodynamic attribution during rollout. |
| Pressure histories | missing | `pressure_gpa` known fraction = `0.0`. | None beyond frame-indexed boundary analysis. | Pressure-resolved mechanism or state-conditioned decomposition claims. |
| Temperature histories | missing | `temperature_k` known fraction = `0.0` in the staged extxyz release. | None beyond subset-level sampling summary. | Temperature-resolved failure analysis within the staged benchmark. |
| Trajectory grouping | missing | `trajectory_id` is effectively frame-unique for both materials. | Deterministic frame-index benchmark split. | Honest trajectory-level leakage-prevention claim. |
| Split policy | available_with_boundary | Current split is deterministic contiguous frame-index `0.8/0.1/0.1` with counts `11851/1481/1482`. | Reproducible benchmark partitioning. | Trajectory-aware generalization claim. |
| Upstream package provenance | available | Staged subset maps to named DeepMD roots `1-CL-20-Total` and `2-HMX-trainset3`. | Chain-of-custody for the data payload and package-to-extxyz conversion. | Full upstream reproducibility by package name alone. |
| DFT labeling settings | available_with_boundary | Provider clarification identifies CP2K, `PBE`, `GTH`, `DZVP-MOLOPT`, Grimme `D3`, and auxiliary plane-wave cutoffs of `60/400 Ry`, but not a reviewer-complete archived `k`-point and workflow record for the exact packaged subset. | Real force-labeled benchmark with a substantially clearer labeling baseline. | Reviewer-complete upstream electronic-structure reproducibility. |
| Small-cell filter rationale | available_with_boundary | Roughly half of original CL-20 and about one sixth of original HMX were removed under the collaboration team's empirical rule that periodic structures with any cell edge below `10 Å` should not enter the final benchmark. | Quality-control justification for the `<10 Å` filter. | Full frame-by-frame re-audit of discarded labels. |
| Shock/compression generation route | incomplete | Current release preserves `decomposition`-regime labels, but not a reviewer-complete generation workflow. | Frame-dominated nonequilibrium boundary on real target structures. | Pressure-history- or loading-history-resolved mechanistic attribution. |

## Practical takeaway

The benchmark already supports the manuscript's central claim about static ranking and nonequilibrium failure boundaries on real CL-20/HMX configurations. It does not yet support pressure-resolved, temperature-resolved, trajectory-history-resolved, or reviewer-complete upstream DFT reproducibility claims.
