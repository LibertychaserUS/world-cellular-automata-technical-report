# Build Notes

## PDF Builder

The PDFs in this package were built with bundled Tectonic 0.16.9 through the
Codex LaTeX compile workflow.

## English Report

- Source: `latex/wca_technical_report_en.tex`
- Output: `pdf/wca_technical_report_en.pdf`

## Chinese Report

- Source: `latex/wca_technical_report_zh.tex`
- Output: `pdf/wca_technical_report_zh.pdf`

The Chinese source uses XeLaTeX-style CJK font configuration and was compiled
with locally available system fonts. If rebuilding on a different operating
system, install an available CJK font and adjust the `xeCJK` font settings if
needed.

## Warnings

The current build emits minor underfull/overfull line-box warnings. These are
layout warnings, not build failures. The generated PDFs were opened through the
system PDF thumbnail renderer for a basic visual smoke check.

