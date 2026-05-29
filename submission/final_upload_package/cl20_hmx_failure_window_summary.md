# CL-20/HMX Failure-Window Summary

Dense fragile-window dynamics analysis resolving the narrow `64–72` local window, comparing `static_charge` against `self_consistent_train_matched` with five seeds on frames `56`, `64`, and `72`.

| Frame | train-matched onset delta | train-matched first-integrity delta | train-matched final-integrity delta | train-matched nitro delta | train-matched vs short-range final-integrity delta |
| ---: | ---: | ---: | ---: | ---: | ---: |
| 56 | -12.0 | 2.0 | -0.027 | -0.100 | -0.014 |
| 64 | -34.0 | -112.0 | 0.083 | 0.000 | 0.010 |
| 72 | -18.0 | 195.0 | 0.058 | 0.008 | 0.087 |

Interpretation:

- The dense analysis rejects a broad onset-gain story: train-matched self-consistency is earlier than `static_charge` on the first short-bond event for all three frames.
- The positive signal reorganizes around endpoint survival instead. Frames `64` and `72` both show higher final molecular integrity for `self_consistent_train_matched` than for `static_charge`.
- Frame `72` is the cleanest local gain window because it combines a higher final integrity (`+0.058`) with a later first integrity crossing (`+195` steps) and a small positive nitro-survival increment.
- Frame `56` remains unfavorable, so the result should be framed as a narrow endpoint-survival window rather than a general dynamic hierarchy.
