---
pretty_name: "World Cellular Automata Technical Report"
language:
  - en
  - zh
license: mit
task_categories:
  - time-series-forecasting
  - image-to-image
tags:
  - world-model
  - cellular-automata
  - physical-field-prediction
  - pdebench
  - weatherbench
  - technical-report
---

# World Cellular Automata Technical Report v0.1

This release contains the public technical report package for World Cellular
Automata (WCA): a recursive local-world architecture for world-state modeling.

## Related Public Repositories

- Code and reproducible experiment entrypoints:
  <https://github.com/LibertychaserUS/world-cellular-automata>
- Technical report, PDFs, LaTeX, figures, tables, and release package:
  <https://github.com/LibertychaserUS/world-cellular-automata-technical-report>
- Hugging Face report/artifact mirror:
  <https://huggingface.co/datasets/Chaser111/world-cellular-automata-technical-report>

## What WCA Is

WCA represents a world state as node vectors, expands that state into a family
of node-centered local worlds, evolves those local worlds through learned pair
interactions, and recomposes evolved centers into the next global state.

The core semantic contract is:

```text
H_t [B,N,D]
  -> L_t [B,N,N,D]
  -> dense local-world pair evolution with semantic [B,N,N,N,D]
  -> center recomposition
  -> H_{t+1} [B,N,D]
```

## Release Contents

- `wca_technical_report_en.pdf`: English technical report.
- `wca_technical_report_zh.pdf`: Chinese technical report.
- `latex/`: LaTeX sources.
- `figures/`: Figures used by the report.
- `tables/`: Main result table.
- `model_card.md`: WCA architecture/model card.
- `dataset_and_artifact_card.md`: Dataset, split, artifact, and evaluation-card summary.
- `zenodo_metadata.json`: Draft Zenodo metadata.
- `CITATION.cff`: Citation metadata template.
- `release_manifest.json`: File hashes for this release package.

## Main Claim

WCA is a credible early architecture primitive for recursive world-state
modeling. Current evidence is strongest in token-level PDEBench
reaction-diffusion, where recursion depth, learnable interfaces, attribution
controls, and h8x2 rollout diagnostics support WCA-core contribution beyond
interface-only and no-recursion controls.

## Evidence Status

- Formal current row: V25d h8x2 token-level rollout.
- Source-audit attribution: V25e-r3 learnable-interface controls.
- Establish-stage evidence: V25 recursion-depth ladder.
- Secondary evidence: maze potential fields and WeatherBench-style real-field transfer.
- Diagnostic boundary: N=256 PatchMean underperformance.

## Recommended Citation

Use the metadata in `CITATION.cff`. Replace placeholder author fields before
formal archive submission if individual authorship should be listed.
