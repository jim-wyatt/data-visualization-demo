# Chromium Headless

## Overview

**Headless Chromium** (or Google Chrome) can render HTML and export to PDF programmatically without a GUI. This is a modern, fast alternative to LaTeX and works reliably across platforms.

## Prerequisites

1. HTML file exported (see [HTML Export + Browser Print](./html-print.md)).
2. Chromium or Google Chrome installed (see [Installation](../installation.md#chromiumgoogle-chrome-for-headless-htmlpdf)).

## CLI Usage

### Basic Command

```bash
chromium --headless --disable-gpu --print-to-pdf=output.pdf data-visualization-demo.html
```

Or with Google Chrome:

```bash
google-chrome --headless --disable-gpu --print-to-pdf=output.pdf data-visualization-demo.html
```

This creates `output.pdf`.

## Options

- `--print-to-pdf=<path>` — output PDF path (required).
- `--print-to-pdf-margin-top=<mm>` — top margin in millimeters.
- `--print-to-pdf-margin-bottom=<mm>` — bottom margin.
- `--print-to-pdf-margin-left=<mm>` — left margin.
- `--print-to-pdf-margin-right=<mm>` — right margin.
- `--print-to-pdf-paper-width=<mm>` — paper width (default 210 for A4).
- `--print-to-pdf-paper-height=<mm>` — paper height (default 297 for A4).
- `--print-to-pdf-prefer-css-page-size` — respect CSS page size if defined.

Example with custom margins:

```bash
chromium --headless --disable-gpu \
  --print-to-pdf=output.pdf \
  --print-to-pdf-margin-top=10 \
  --print-to-pdf-margin-bottom=10 \
  data-visualization-demo.html
```

## Automated in the Notebook

The notebook includes a Python cell that automates this process:
1. Looks for Chromium/Chrome on your PATH.
2. Detects the HTML file.
3. Runs the headless print-to-pdf command.
4. Reports success or suggests alternatives.

## Advantages

- **No LaTeX:** Avoids system dependency complexity.
- **Fast:** PDF generation is quick (seconds).
- **Reliable:** Chromium's rendering engine is modern and well-tested.
- **Portable:** Works on Linux, macOS, Windows.
- **Customizable:** Fine control over margins, page size, and other parameters.

## Troubleshooting

**Error: "Chromium not found"**
- Install Chromium or Chrome (see [Installation](../installation.md#chromiumgoogle-chrome-for-headless-htmlpdf)).
- Verify it's on your PATH: `which chromium` or `which google-chrome`.

**Sandbox errors (Docker/WSL)**
- If sandboxing fails, try without `--no-sandbox` (be aware of security implications):
  ```bash
  chromium --headless --no-sandbox --disable-gpu --print-to-pdf=output.pdf file.html
  ```

**PDF is blank**
- Ensure the HTML file is valid and self-contained. Plotly charts with CDN URLs should work.
- Try opening the HTML in a browser first to confirm it renders.

## See Also

- Chromium docs: [headless-mode](https://chromium.googlesource.com/chromium/src/+/lkgm/headless/README.md)
- Supported flags: `chromium --help | grep print-to-pdf`
