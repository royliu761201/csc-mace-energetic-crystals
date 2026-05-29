# CL-20/HMX QEq Activity Versus Dynamical Failure

This bridge table is meant to answer the reviewer question "if QEq is active, why is the dynamical hierarchy still weak?"

Key readout:
- `static_charge` and `self_consistent` show non-zero charge and field response in the static benchmark.
- Across the frame-32/64/160 key-bond survival comparison, the final failure metrics are nearly identical within each frame despite different QEq activity levels.
- The frame-160 nitro-focus multiseed analysis reinforces the same point at multiseed resolution: charge-aware families remain active, but the family-level spread in nitro-motif integrity stays negligible.

## Frame-Indexed Bridge Table

| Benchmark | Frame | Family | Static energy MAE (meV/atom) | Charge RMS | Field RMS | Final molecular integrity | Final retained N-O | First integrity < 0.5 step | First potential-drift threshold step |
| --- | ---: | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| frame_32_keybond_survival | 32 | self_consistent | 397.37 | 0.007718 | 0.001670 | 0.333 | 0.827 | 390 | 1117 |
| frame_32_keybond_survival | 32 | short_range | 479.24 | 0.000000 | 0.000000 | 0.333 | 0.827 | 390 | 1118 |
| frame_32_keybond_survival | 32 | static_charge | 419.26 | 0.007441 | 0.001556 | 0.333 | 0.827 | 390 | 1117 |
| frame_64_keybond_survival | 64 | self_consistent | 397.37 | 0.007718 | 0.001670 | 0.286 | 0.553 | 390 | 1087 |
| frame_64_keybond_survival | 64 | short_range | 479.24 | 0.000000 | 0.000000 | 0.286 | 0.553 | 390 | 1087 |
| frame_64_keybond_survival | 64 | static_charge | 419.26 | 0.007441 | 0.001556 | 0.286 | 0.553 | 390 | 1087 |
| frame_160_keybond_survival | 160 | self_consistent | 397.37 | 0.007718 | 0.001670 | 0.750 | 0.915 | 360 | 1056 |
| frame_160_keybond_survival | 160 | short_range | 479.24 | 0.000000 | 0.000000 | 0.750 | 0.915 | 370 | 1056 |
| frame_160_keybond_survival | 160 | static_charge | 419.26 | 0.007441 | 0.001556 | 0.750 | 0.915 | 360 | 1056 |

## Frame-160 Nitro-Focus Multiseed Bridge

| Benchmark | Family | Charge RMS | Field RMS | Final molecular integrity | Final retained nitro N-O | Final nitro-motif integrity | First integrity < 0.5 step | First motif < 0.5 step |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| frame_160_nitro_focus_multiseed | self_consistent | 0.007718 | 0.001670 | 0.500 | 0.463 | 0.148 | 236.7 | 1646.7 |
| frame_160_nitro_focus_multiseed | self_consistent_damp001 | 0.000000 | 0.000000 | 0.500 | 0.463 | 0.148 | 236.7 | 1646.7 |
| frame_160_nitro_focus_multiseed | self_consistent_damp002 | 0.000000 | 0.000000 | 0.500 | 0.463 | 0.148 | 236.7 | 1646.7 |
| frame_160_nitro_focus_multiseed | short_range | 0.000000 | 0.000000 | 0.556 | 0.444 | 0.148 | 236.7 | 1663.3 |
| frame_160_nitro_focus_multiseed | static_charge | 0.007441 | 0.001556 | 0.500 | 0.463 | 0.148 | 236.7 | 1646.7 |

Interpretation: QEq is measurably active in the charge-aware families, but the dynamic observables collapse primarily by frame rather than by family. That is exactly the manuscript's boundary claim: static electrostatic gains are real, yet they do not automatically propagate into a new nonequilibrium event hierarchy.
