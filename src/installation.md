# Installation

## Python Packages (Required)

### Using a Virtual Environment (Recommended)

Create a fresh Python environment to isolate this project's dependencies:

```bash
cd /path/to/data-visualization-demo
python -m venv .venv
```

**Activate the virtual environment:**

- **Linux/macOS:**
  ```bash
  source .venv/bin/activate
  ```

- **Windows (PowerShell):**
  ```powershell
  .\.venv\Scripts\Activate.ps1
  ```

- **Windows (Command Prompt):**
  ```cmd
  .venv\Scripts\activate.bat
  ```

### Install Dependencies

With the virtual environment activated, install all required Python packages:

```bash
pip install -r requirements.txt
```

This installs ~75 packages including:
- **Jupyter Lab / Notebook** (latest)
- **Matplotlib 3.10.7** — static plotting
- **Seaborn 0.13.2** — statistical visualization
- **Plotly 6.4.0** — interactive web charts
- **Pandas 2.3.3** — data manipulation
- **NumPy 2.3.4** — numerical computing
- **Datashader 0.18.2** — large dataset aggregation
- **Statsmodels 0.14.5** — regression and statistics
- And ~50+ supporting libraries (see `requirements.txt` for full list).

## System Packages (Optional)

Depending on which features you want to use, you may need to install additional system-level packages.

### LaTeX (for Direct PDF Export)

Required for `jupyter nbconvert --to pdf`.

**Debian/Ubuntu:**
```bash
sudo apt update
sudo apt install -y texlive-xetex texlive-fonts-recommended texlive-latex-recommended
```

**macOS (with Homebrew):**
```bash
brew install mactex
```

**Windows:**
Download and install MiKTeX or TeX Live from their official sites.

### Chromium / Google Chrome (for Headless HTML→PDF)

Alternative to LaTeX; recommended for environments where TeX is difficult to install.

**Debian/Ubuntu:**
```bash
sudo apt update
sudo apt install -y chromium-browser
```

**macOS (with Homebrew):**
```bash
brew install chromium
```

**Windows:**
Download from [Google Chrome](https://www.google.com/chrome/) or [Chromium](https://www.chromium.org/getting-involved/download-chromium/).

### ffmpeg (for Animation Export to MP4)

**Debian/Ubuntu:**
```bash
sudo apt install -y ffmpeg
```

**macOS (with Homebrew):**
```bash
brew install ffmpeg
```

**Windows:**
Download from [ffmpeg.org](https://ffmpeg.org/download.html) or install via Chocolatey:
```cmd
choco install ffmpeg
```

## Verification

To verify your installation, activate your virtual environment and run:

```bash
python -c "import jupyter, matplotlib, seaborn, plotly; print('All core packages imported successfully!')"
jupyter --version
```

You should see version information for Jupyter and no errors.

## Next: Running the Notebook

Once installed, see [Running the Notebook](./running-notebook.md) to get started.
