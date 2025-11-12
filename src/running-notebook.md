# Running the Notebook

## Prerequisites

Ensure you have:
1. Installed Python packages (see [Installation](./installation.md)).
2. Activated your virtual environment.

## Starting Jupyter

From the project directory, activate your environment and launch Jupyter:

### Using Jupyter Lab (Recommended)

```bash
jupyter lab
```

Your browser should open automatically to `http://localhost:8888` (or a similar URL with a token).

### Using Jupyter Notebook

```bash
jupyter notebook
```

## Opening the Notebook

1. In the Jupyter file browser, navigate to and click on `data-visualization-demo.ipynb`.
2. The notebook will open in a new tab.

## Running Cells

- **Run a single cell:** Click the cell and press `Ctrl+Enter` (or `Cmd+Enter` on macOS).
- **Run all cells:** From the menu, select *Run* → *Run All Cells*.
- **Run from a specific point:** Click a cell and select *Run* → *Run All Below*.

## Key Sections

The notebook is organized as follows:

1. **Setup** — Import libraries and install missing dependencies (run this first).
2. **Load Datasets** — Load iris, tips, and flights datasets from Seaborn.
3. **Visualization Examples** — Various chart types (line, scatter, histogram, heatmap, etc.).
4. **Interactive Plots** — Plotly examples with HTML export fallbacks.
5. **Animations** — Matplotlib FuncAnimation with MP4/GIF export.
6. **Exporting to PDF** — Multiple approaches for notebook→PDF conversion.

## Troubleshooting

**"Kernel died" or "Import error"**
- Ensure you activated the virtual environment before launching Jupyter.
- Try restarting Jupyter and running the Setup cell again.

**Plots not showing inline**
- Confirm `%matplotlib inline` is in the setup cell and has been executed.

**Memory or performance issues**
- The datashader example creates a large synthetic dataset. Reduce the `mult` variable in that cell if your system is resource-constrained.

For more help, see [Troubleshooting](../troubleshooting.md).
