# Submission Package

## Target journal

- `npj Computational Materials`

## Primary upload files

- Main manuscript PDF:
  - [csc_mace.pdf](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/csc_mace.pdf)
- Cover letter:
  - [cover_letter_npjsubmission.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cover_letter_npjsubmission.md)
  - Short paste-ready version: [cover_letter_npjsubmission_short.txt](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cover_letter_npjsubmission_short.txt)

## Metadata to verify before upload

- Title in manuscript:
  - `Charge-self-consistent equivariant potentials for energetic molecular crystals: static gains and nonequilibrium limits`
- First author:
  - `Xiaohua Liu`
- Second author:
  - `Dongping Chen`
- Third author:
  - `Chengkai Zhang`
- Fourth author:
  - `Hongqian Sang`
- Corresponding author:
  - `Xiaohua Liu`
- Corresponding email:
  - `xiaohualiu@jhun.edu.cn`
- Affiliations:
  - `State Key Laboratory of Precision Blasting, Jianghan University, Wuhan 430056, Hubei, China`
  - `State Key Laboratory of Explosion Science and Safety Protection, Beijing Institute of Technology, Beijing 100081, China`

## Recommended supplementary evidence set

- Target-data provenance note:
  - [cl20_hmx_target_data_provenance_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_target_data_provenance_note.md)
  - Author-team-confirmed sampling: scale factors `0.96/1.00/1.04`, temperatures `300/500/1000/2000/3000/4000 K`, retained systems matchable to concrete temperature/scale conditions by frame order, no relabeling after receipt, and a collaboration quality-control filter excluding periodic structures with any cell edge below `10 Å`, consistent with Wen et al., *Phys. Chem. Chem. Phys.* 2024, 26, 9984--9997.
- Target split-upgrade note:
  - [cl20_hmx_target_split_upgrade_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_target_split_upgrade_note.md)
  - Documents the new target-specific material-balanced metadata/split bundle at `data/metadata/cl20_hmx_target_v1`.
  - The additional GPU evaluation on that cleaner split now preserves the same static family ordering on a jointly held-out CL-20/HMX test mix: `self_consistent 22704.77 < static_charge 23026.01 < short_range 23557.23` on energy MAE.
- Block-holdout split-v3 summary:
  - [cl20_hmx_target_split_v3_summary.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_target_split_v3_summary.md)
  - [cl20_hmx_target_split_v3_summary.json](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_target_split_v3_summary.json)
  - Documents the stronger order-recovered block holdout over author-team-confirmed `scale x temperature` buckets; the GPU evaluation again preserves the same static family ordering on the held-out `4000 K` buckets: `self_consistent 22611.09 < static_charge 22913.15 < short_range 23421.07` on energy MAE.
- Temperature-gap split-v4 summary:
  - [cl20_hmx_target_split_v4_summary.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/data/metadata/cl20_hmx_target_v4/cl20_hmx_target_split_v4_summary.md)
  - [cl20_hmx_split_v4_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_split_v4_note.md)
  - Documents the stronger recovered temperature-gap holdout with `3000 K` buckets held out for validation and `4000 K` buckets held out for test; the GPU evaluation again preserves the same static family ordering: `self_consistent 22450.66 < static_charge 22744.22 < short_range 23241.62` on energy MAE.
- External method anchor:
  - [cl20_hmx_external_method_anchor_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_external_method_anchor_note.md)
- Benchmark-boundary table:
  - [cl20_hmx_benchmark_boundary_table.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_benchmark_boundary_table.md)
  - [cl20_hmx_benchmark_boundary_table.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_benchmark_boundary_table.csv)
  - Structured as a reviewer-facing support-boundary table with explicit “claim supported now / claim not supported yet” columns.
- QEq diagnostics:
  - [cl20_hmx_target_qeq_diagnostics_summary.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_target_qeq_diagnostics_summary.md)
  - [cl20_hmx_target_qeq_diagnostics_summary.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_target_qeq_diagnostics_summary.csv)
  - [cl20_hmx_qeq_numerical_details.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_qeq_numerical_details.md)
  - [cl20_hmx_qeq_stress_conditioning_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_qeq_stress_conditioning_note.md)
- Split-by-material held-out table:
  - [cl20_hmx_split_by_material_table.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_split_by_material_table.md)
  - [cl20_hmx_split_by_material_table.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_split_by_material_table.csv)
  - This table is now confirmed by a six-variant GPU evaluation of the static multiseed comparison, but under the current deterministic contiguous split it is an `HMX`-only held-out slice rather than a simultaneous held-out `CL-20/HMX` comparison.
- QEq-versus-failure bridge:
  - [cl20_hmx_qeq_failure_bridge.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_qeq_failure_bridge.md)
  - [cl20_hmx_qeq_failure_bridge.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_qeq_failure_bridge.csv)
- Frame-versus-family dominance summary:
  - [cl20_hmx_frame_family_dominance.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_frame_family_dominance.md)
  - [cl20_hmx_frame_family_dominance.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_frame_family_dominance.csv)
  - Compresses the main final-target dynamical result into a direct comparison of within-frame family spread versus within-family frame spread.
- Onset-to-drift margin table:
  - [cl20_hmx_onset_margin_table.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_onset_margin_table.md)
  - [cl20_hmx_onset_margin_table.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_onset_margin_table.csv)
  - Recasts the final-target dynamics result as a mechanism-facing timing pattern: onset and endpoint behavior do not move together, so local timing changes need to be interpreted alongside final structural survival rather than as a standalone onset gain.
- Force-norm increment table:
  - [cl20_hmx_force_norm_increment_table.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_force_norm_increment_table.md)
  - [cl20_hmx_force_norm_increment_table.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_force_norm_increment_table.csv)
  - Pairs `static_charge` and `self_consistent` on the same frame and seed to show whether explicit self-consistency changes the earliest force-norm path before later structural degradation.
- Adaptive-gate cost-versus-outcome:
  - [cl20_hmx_adaptive_gate_cost_table.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_adaptive_gate_cost_table.md)
  - [cl20_hmx_adaptive_gate_cost_table.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_adaptive_gate_cost_table.csv)
  - [cl20_hmx_rollout_overhead_summary.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_rollout_overhead_summary.md)
  - [cl20_hmx_rollout_overhead_summary.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_rollout_overhead_summary.csv)
  - [cl20_hmx_family_overhead_status_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_family_overhead_status_note.md)
  - [cl20_hmx_gpu_static_overhead_proxy.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_gpu_static_overhead_proxy.md)
  - [cl20_hmx_gpu_static_overhead_proxy.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_gpu_static_overhead_proxy.csv)
  - [cl20_hmx_gpu_static_overhead_proxy.tex](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_gpu_static_overhead_proxy.tex)
- Nitro-focus table:
  - [cl20_hmx_nitro_focus_table.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_nitro_focus_table.md)
  - [cl20_hmx_nitro_focus_table.tex](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_nitro_focus_table.tex)
- Breakdown-threshold summary:
  - [cl20_hmx_breakdown_threshold_summary.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_breakdown_threshold_summary.md)
  - [cl20_hmx_breakdown_threshold_summary.csv](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_breakdown_threshold_summary.csv)
  - Shows that the broader onset-style breakdown comparison still yields no positive `self_consistent > static_charge` zone on frames `64/128/192`.
- Failure-manifold summary:
  - [cl20_hmx_failure_manifold_summary.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_failure_manifold_summary.md)
  - [cl20_hmx_failure_manifold_summary.json](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_failure_manifold_summary.json)
  - Records the first fragile-manifold scan that motivated the denser failure-window analysis; the final manuscript-level dynamic claim is now carried by the narrower `64–72` endpoint-survival window rather than by a standalone onset gain.
- Failure-window summary:
  - [cl20_hmx_failure_window_summary.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_failure_window_summary.md)
  - [cl20_hmx_failure_window_summary.json](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_failure_window_summary.json)
  - [cl20_hmx_failure_window_aggregate_summary.json](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_failure_window_aggregate_summary.json)
  - Refines the fragile-frame story into a narrow endpoint-survival window: frames `64` and `72` improve final molecular integrity relative to `static_charge`, with the clearest local gain on frame `72`, while frame `56` remains unfavorable.

## Internal review materials

- Reviewer FAQ:
  - [reviewer_faq.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/reviewer_faq.md)
- Final-target dynamics takeaway:
  - [cl20_hmx_dynamics_takeaway.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_dynamics_takeaway.md)
- Split-v3 note:
  - [cl20_hmx_split_v3_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_split_v3_note.md)
- Failure-manifold analysis plan:
  - [cl20_hmx_failure_manifold_suite_plan.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_failure_manifold_suite_plan.md)
- Failure-window plan:
  - [cl20_hmx_failure_window_plan.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_failure_window_plan.md)
- Self-consistency increment note:
  - [self_consistency_increment_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/self_consistency_increment_note.md)
- Train/inference self-consistency mismatch note:
  - [self_consistency_train_inference_mismatch_note.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/self_consistency_train_inference_mismatch_note.md)
- Train-matched dynamics ablation plan:
  - [cl20_hmx_train_matched_dynamics_plan.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_train_matched_dynamics_plan.md)
- Train-matched dynamics readout checklist:
  - [cl20_hmx_train_matched_readout_checklist.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/cl20_hmx_train_matched_readout_checklist.md)
  - The completed frame-160 GPU ablation shows that re-aligning the rollout to the stronger static-side self-consistent settings does not create a family-level dynamics win: drift threshold `1067 -> 1058`, final molecular integrity `0.583 -> 0.583`, retained `N-O` `0.903 -> 0.887`.
- Train-matched dynamics status:
  - [cl20_hmx_train_matched_status.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_train_matched_status.md)
- Combined GPU campaign status:
  - [cl20_hmx_gpu_campaign_status.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/results/target/cl20_hmx_gpu_campaign_status.md)
- Method-reviewer prebuttal:
  - [method_reviewer_prebuttal.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/method_reviewer_prebuttal.md)
- Final pressure test:
  - [npjcm_final_pressure_test.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/npjcm_final_pressure_test.md)
- Major concerns response:
  - [npjcm_major_concerns_response.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/npjcm_major_concerns_response.md)
- Full manuscript file index:
  - [manuscript_files.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/manuscript_files.md)
- Submission checklist:
  - [submission_checklist.md](/Users/roy-jd/workspace/projects_core/CSC_MACE/paper/submission/submission_checklist.md)

## Known residual risk

- The main unresolved external risk is still the missing reviewer-complete `CL-20/HMX` DFT/shock reproducibility metadata record.
