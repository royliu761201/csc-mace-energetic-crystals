# CL-20/HMX Split-V3 Note

- status: `implemented`
- claim level: `cleaner block holdout, not trajectory-clean`

This split upgrades the target benchmark beyond the original HMX-only contiguous slice and beyond the material-balanced split-v2 by holding out author-team-recovered `material x scale x temperature` order buckets rather than isolated contiguous ranges. The recovered groups follow the confirmed within-material write order:

`0.96 -> 300, 500, 1000, 2000, 3000, 4000 K`, then `1.00 -> ...`, then `1.04 -> ...`

Boundary:

- The recovered scale/temperature groups are stronger than pure contiguous slicing.
- The split is still not trajectory-clean because upstream trajectory-history metadata remain unavailable.
- Paper-facing wording should therefore describe split-v3 as an `order-recovered block holdout`.
