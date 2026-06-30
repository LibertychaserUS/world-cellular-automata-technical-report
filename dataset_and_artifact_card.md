# Dataset and Artifact Card

## Primary Benchmark

The primary strict evidence in this report uses PDEBench reaction-diffusion.
The field has two channels over a 128 by 128 grid. The formal report focuses on
token-level contracts, especially h8 and h8x2 rollout diagnostics.

## Split Principle

PDEBench reaction-diffusion data are trajectory-based. Formal splits must assign
whole trajectories to train, validation, and test before constructing temporal
windows. Frame-level flatten-and-split is not valid for formal evidence because
it can leak trajectory identity and produce windows that cross trajectory
boundaries.

## Horizon Principle

The main horizons are h1, h2, h4, and h8. Formal comparisons require matching:

- split manifest;
- evaluation start indices;
- token geometry;
- patch size;
- horizon-conditioning contract;
- checkpoint policy;
- metric space.

Same seed or same sample count alone is not sufficient for formal comparison.

## Metric Space

WCA token-level predictions and raw/full-field baselines may answer different
metric questions. Formal comparisons must state whether the metric is:

- token-space;
- native full-field;
- downsampled full-field;
- patch-repeated visualization only.

The current strongest manuscript row is token-level. Mixed qualitative panels
are diagnostic and should not be used as native full-field superiority claims.

## Reported Evidence Classes

| Evidence class | Meaning |
|---|---|
| Formal | Completed strict protocol for the stated row. |
| Source-audit | Useful attribution evidence, not yet promoted to formal horizon statistics. |
| Establish-stage | Directional architecture evidence that motivates stricter follow-up. |
| Secondary | Supports plausibility or transfer but is not the primary formal claim. |
| Diagnostic | Exposes boundary, failure, or future requirement. |

## Current Artifact Package

This release package includes only public report assets: LaTeX sources, PDFs,
figures, tables, metadata, and hash manifests. It does not include private
machine paths, remote access details, or raw training infrastructure logs.

