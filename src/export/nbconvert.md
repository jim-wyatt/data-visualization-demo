# Direct PDF via nbconvert

## Overview

**nbconvert** is Jupyter's official tool for converting notebooks to various formats. Using the `--to pdf` option generates a PDF via a LaTeX intermediate.

## Prerequisites

1. Jupyter and nbconvert installed (both in `requirements.txt`).
2. LaTeX installed on your system (see [Installation](../installation.md#latex-for-direct-pdf-export)).

## CLI Usage

From the project directory:

```bash
jupyter nbconvert --to pdf data-visualization-demo.ipynb
```

This creates `data-visualization-demo.pdf` in the same directory.

## Options

- `--output-dir=./output` — specify output directory.
- `--no-input` — exclude input cells (show only output).
- `--template=classic` — use different templates.
- `--execute` — re-run all cells before export (slow for large notebooks).

Example:

```bash
jupyter nbconvert --to pdf --no-input --output-dir=./pdf-output data-visualization-demo.ipynb
```

## Troubleshooting

**Error: "xelatex not found"**
- LaTeX is not installed. See [Installation](../installation.md#latex-for-direct-pdf-export) for platform-specific steps.

**Error: "PDF was not created"**
- Complex plots or Unicode may cause LaTeX issues. Try simplifying or using alternative fonts.
- Use `--debug` flag for verbose output: `jupyter nbconvert --debug --to pdf ...`

**Performance:**
- First run is slow (LaTeX compilation takes ~30s). Subsequent runs are faster.

## When to Use

- **Simple, static documents** with standard plots.
- **Archival:** guaranteed PDF output format (backward compatible).
- **CI/CD pipelines:** if LaTeX is already available in your environment.

## See Also

- nbconvert: [sphinx.nbconvert.readthedocs.io](https://nbconvert.readthedocs.io/)
