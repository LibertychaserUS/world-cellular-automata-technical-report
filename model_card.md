# WCA Architecture Card

## Model Name

World Cellular Automata (WCA), protected baseline family: Full Dense RWS-NCA.

## Intended Research Use

WCA is intended for research on recursive world-state prediction. Current tasks
include structured maze potential-field prediction, PDEBench reaction-diffusion
field prediction, and WeatherBench-style multivariate field prediction.

## Architecture Summary

The protected WCA baseline maintains a hidden world state:

```text
H_t: [B,N,D]
```

It constructs a bundle of local worlds:

```text
L_t: [B,N,N,D]
```

Pair dynamics inside local worlds have semantic shape:

```text
[B,N,N,N,D]
```

The evolved center diagonal is recomposed into:

```text
H_{t+1}: [B,N,D]
```

## Core Invariants

- The center index in `L_t` is semantically meaningful.
- Pair evolution acts inside each center-indexed local world.
- Recomposition uses evolved centers.
- Dense semantics may be chunked for memory only when the mathematical behavior
  is preserved.
- Sparse, hybrid, multiscale, egocentric, RL, or memory variants are explicit
  variants, not silent replacements of the baseline.

## Current Best-Supported Use

Token-level physical field prediction under controlled PDEBench
reaction-diffusion contracts, especially long-horizon h8 and h8x2 rollout
diagnostics with learnable patch interfaces.

## Known Limits

- Current formal evidence is primarily token-level.
- Patch-repeated WCA visualizations do not represent native full-field detail.
- N=256 PatchMean underperformed matched token baselines under current capacity
  and interface conditions.
- Broader PDE families, native rollout, and larger multi-seed replications are
  required for stronger claims.

## Training Feedback

The current experiments use supervised gradient-based learning. Metrics are
used for evaluation and checkpoint selection, not as reinforcement rewards or
intrinsic-drive signals.

