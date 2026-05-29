# CL-20/HMX Split V4 Note

This note records the stronger target split attempted after split-v3.

- Policy: `order_recovered_temperature_gap_holdout_v4`
- Recovery basis: author-team-confirmed within-material write order over `scale x temperature`
- Validation groups: recovered `3000 K` buckets
- Test groups: recovered `4000 K` buckets

Interpretation:

- Split-v4 is stronger than split-v3 because both validation and test are separated from training by a recovered temperature gap.
- It still should not be described as trajectory-clean, because explicit upstream trajectory-history metadata remain unavailable.
