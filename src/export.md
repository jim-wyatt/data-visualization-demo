# Exporting & PDF Generation

## Overview

Converting a Jupyter notebook to a shareable PDF is a common task. This documentation covers three approaches:

1. **Direct PDF via nbconvert** (simplest, requires LaTeX).
2. **HTML export + browser print** (universal, manual step).
3. **Automated headless Chromium** (modern, no LaTeX).

## Quick Links

- [Direct PDF via nbconvert](./nbconvert.md)
- [HTML + Browser Print](./html-print.md)
- [Chromium Headless](./chromium.md)

## Comparison

| Method | Ease | Speed | Requirements | Notes |
|--------|------|-------|--------------|-------|
| nbconvert PDF | Easy | Fast | LaTeX | Fails if LaTeX missing |
| HTML + Print | Medium | Medium | Browser | Manual step; good UI control |
| Chromium | Medium | Fast | Chromium | Fully automated; modern alternative to LaTeX |

## Choosing the Right Method

- **If LaTeX is installed:** Use nbconvert for simplicity.
- **If you prefer a UI:** Export to HTML and use browser Print dialog.
- **If you want full automation without LaTeX:** Use headless Chromium.

All three methods are implemented as helper cells in the notebook for easy access.
