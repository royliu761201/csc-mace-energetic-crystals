# CL-20/HMX Dynamics Takeaway

This note compresses the final-target dynamics conclusion into one editor-facing message.

## One-sentence claim

`On the real CL-20/HMX target, charge-aware models improve the static energy hierarchy, and train-matched self-consistency can improve endpoint structural survival within a narrow local window around frames 64--72, but the overall nonequilibrium event hierarchy remains controlled primarily by starting-frame choice rather than by model family.`

## Minimal evidence chain

1. Static target result:
   - `self_consistent` gives the best energy MAE
   - `static_charge` is second
   - `short_range` is weakest
   - force MAE is effectively tied
   - the same ordering now survives the original contiguous slice, the cleaner split-v2 evaluation, the stronger order-recovered block-holdout split-v3 evaluation, and the stronger recovered temperature-gap split-v4 evaluation

2. Charge mechanism is active:
   - charge-aware families show non-zero charge and field response
   - neutrality residuals remain numerically negligible

3. Final-target dynamics stay frame-dominated:
   - on frames `32`, `64`, and `160`, final molecular integrity and retained bond fractions are nearly unchanged across the three main families within each frame
   - across those same frames, each family spans much larger changes
   - the mean spread across frames is about `8x` larger than the family spread for the first integrity-crossing step
   - the mean spread across frames is about `184x` larger than the family spread for the first drift-threshold step

4. Stronger charge-aware variants do not break the boundary:
   - the frame-160 nitro-focus multiseed analysis preserves the same interpretation
   - adaptive gating increases rollout cost without producing a new structure-survival hierarchy
   - the denser failure-window analysis rejects a broad onset-gain story but reveals a narrow endpoint-survival window on frames `64–72` instead
   - frames `64` and `72` both improve final molecular integrity for `train-matched self_consistent` relative to `static_charge`
   - frame `72` is the cleanest local gain, combining higher final integrity, a later first-integrity crossing, and a small nitro-survival increase

## Safe interpretation

This is not evidence that charge self-consistency is inert. It is evidence that:

- static electrostatic gains are real
- those gains are measurable on the final energetic-material target
- endpoint-level nonequilibrium help can appear within a narrow local window around frames `64–72`
- under the current rollout protocols, they do not yet dominate the nonequilibrium outcome

## Best use in submission

Use this note when you need a short consistent answer for:

- editor pitch
- cover letter
- reviewer FAQ
- oral explanation of the paper's main limitation and value
