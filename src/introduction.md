# Introduction

Welcome to the **Data Visualization Techniques Demo**!

This project showcases a comprehensive set of data visualization techniques using popular Python libraries:
- **Matplotlib** — static plotting and customization
- **Seaborn** — statistical visualization with pandas integration
- **Plotly** — interactive web-based charts
- **Datashader** — rendering very large datasets efficiently

## What's Included

- A Jupyter Notebook (`data-visualization-demo.ipynb`) with live, runnable examples across all major visualization types.
- Interactive HTML exports for Plotly charts that work without a running Python kernel.
- Automated helpers to export the notebook to PDF using `nbconvert` or headless Chromium.
- Examples of exporting animations to MP4/GIF and saving static plots as PNG.
- Comprehensive documentation (this site) for quick reference.

## Key Features

1. **Multi-library coverage** — Matplotlib for low-level control, Seaborn for quick statistical plots, Plotly for interactivity.
2. **Large dataset handling** — Datashader fallback for hexbin aggregation when rendering hundreds of thousands of points.
3. **Export flexibility** — Three approaches to PDF generation: LaTeX-based nbconvert, browser print, or headless Chromium.
4. **Animation support** — FuncAnimation examples with MP4/GIF export options.
5. **Reproducible environment** — Pinned dependencies in `requirements.txt` for exact reproduction.

## Quick Start

1. Clone or download this repository.
2. Set up a Python virtual environment and install dependencies (see [Installation](./installation.md)).
3. Launch Jupyter and open the notebook (see [Running the Notebook](./running-notebook.md)).
4. Run cells to explore visualization techniques and export examples.

For detailed instructions, see [Getting Started](./getting-started.md).

## Next Steps

- Explore [Visualization Techniques](./techniques.md) for explanations of each chart type.
- Learn about [Exporting & PDF Generation](./export.md) to create shareable documents.
- Refer to [Troubleshooting](./troubleshooting.md) if you run into issues.

Happy visualizing!
