# Data Visualization Techniques Demo

This repository contains a Jupyter Notebook demonstrating a variety of data visualization techniques using Matplotlib, Seaborn, and Plotly. It includes examples for static plots, interactive Plotly exports, datashader usage for very large datasets, and helpful utilities for exporting the notebook to PDF.

Files of interest
- `data-visualization-demo.ipynb` — primary notebook with examples and export helper cells.
- `requirements.txt` — pinned Python package dependencies used in the notebook.
- `interactive_tips.html`, `interactive_flights.html` — interactive Plotly HTML exports (created when Plotly inline rendering is unavailable or by notebook code).

Quick overview
- The notebook demonstrates: line plots, scatter + regression, histograms & KDE, box/violinplots, heatmaps & correlations, pairplots, interactive Plotly charts, datashader hex/aggregation fallback, animations with Matplotlib, and export examples.
- Near the end of the notebook there are cells that show how to export the notebook to PDF using `nbconvert`, and an automated Chromium-based HTML->PDF step if LaTeX is not present.

Requirements
- Python 3.10+ (recommended). The notebook has been developed with modern package versions; use the provided `requirements.txt` to reproduce the environment.

Install (recommended)
1. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

2. Install Python dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

System packages (optional / for full functionality)
- LaTeX (for `nbconvert --to pdf`): On Debian/Ubuntu, install a minimal set required by nbconvert PDF exporter:

```bash
sudo apt update
sudo apt install -y texlive-xetex texlive-fonts-recommended texlive-latex-recommended
```

- Chromium / Google Chrome (for headless HTML->PDF conversion): On Debian/Ubuntu you can install Chromium with:

```bash
sudo apt update
sudo apt install -y chromium-browser
```

- ffmpeg (for exporting animations to MP4):

```bash
sudo apt install -y ffmpeg
```

How to run the notebook
1. Activate the virtual environment.
2. Start Jupyter and open the notebook:

```bash
jupyter lab
# or
jupyter notebook
```

Exporting to PDF — three approaches

1) Direct PDF via nbconvert (LaTeX required)

```bash
jupyter nbconvert --to pdf data-visualization-demo.ipynb
```

This is the simplest CLI route but commonly fails if LaTeX is not installed. If it fails, see the fallback approaches.

2) HTML export followed by manual browser Print -> Save as PDF

```bash
jupyter nbconvert --to html data-visualization-demo.ipynb
# Open data-visualization-demo.html in a browser and Print -> Save as PDF
```

3) Automated HTML -> PDF using headless Chromium/Chrome (recommended when LaTeX is not available)

- After exporting HTML (or using the notebook's built-in HTML export), run:

```bash
chromium --headless --disable-gpu --no-sandbox --print-to-pdf=output.pdf data-visualization-demo.html
# or for Google Chrome:
google-chrome --headless --disable-gpu --print-to-pdf=output.pdf data-visualization-demo.html
```

- The notebook contains an automated helper cell that will look for a Chromium/Chrome binary on your PATH and run this headless print-to-pdf command for you. It writes the PDF as `data-visualization-demo.chromium.pdf` by default.

Notes and troubleshooting
- If `jupyter nbconvert --to pdf` fails with LaTeX errors, install the TeX packages listed above or use the Chromium fallback.
- If the Chromium command errors with sandboxing or permission issues inside certain containers, try running without `--no-sandbox` only if you understand the security implications, or run the conversion from a local desktop environment.
- If Plotly interactive charts aren't rendering inline, the notebook already writes HTML files (see `interactive_tips.html` / `interactive_flights.html`) which you can open in a browser.
- Datashader: the notebook attempts to use `datashader`. If unavailable, it falls back to a Matplotlib hexbin and prints install instructions: `pip install datashader colorcet`.
- Animations: exporting to MP4 requires `ffmpeg` on PATH (see installation above). GIF fallback uses Pillow (already in `requirements.txt`).

Customization
- You can change the PDF output name or paper size by editing the headless Chromium command or the helper cell in the notebook. If you want, I can add optional arguments (paper size, margins, scale) to the notebook helper and expose them as variables.

Documentation Site (mdbook)
This repository includes **mdbook** support for a complete, searchable documentation site. The site covers:
- Installation and setup guides.
- Detailed explanations of all visualization techniques.
- Step-by-step export instructions.
- Troubleshooting and tips.

### Building and Serving the Documentation

First, install mdbook (if not already installed):

```bash
cargo install mdbook
# or if you have mdbook via package manager:
# sudo apt install mdbook  (Debian/Ubuntu)
# brew install mdbook      (macOS)
```

Then, from the project directory:

```bash
# Serve locally at http://localhost:3000
mdbook serve

# Or build static HTML (output in ./book/)
mdbook build
```

The documentation provides the same information as the README in a more organized, navigable format. Useful for:
- Exploring examples without running Jupyter.
- Sharing with non-technical stakeholders (static HTML).
- Maintaining detailed reference material.

License
This demo is provided as-is for learning and experimentation. MIT License — see `LICENSE` file.