# Troubleshooting

## Common Issues & Solutions

### Jupyter / Kernel Issues

#### "Kernel died" or "Connection lost"

**Symptoms:** Jupyter stops responding or crashes.

**Solutions:**
1. Restart the kernel: *Kernel* → *Restart* in Jupyter menu.
2. Ensure you activated the virtual environment before launching Jupyter.
3. Check available system memory; large datashader computations consume RAM.
4. Update Jupyter: `pip install --upgrade jupyter ipykernel`.

#### "ImportError: No module named 'X'" or "ModuleNotFoundError"

**Symptoms:** A cell fails with `ImportError` or `ModuleNotFoundError` for a library.

**Solutions:**
1. Install the missing package: `pip install <package_name>` or `pip install -r requirements.txt` for full environment.
2. Ensure the virtual environment is activated: `which python` should show `.venv/bin/python`.
3. Restart the kernel after installing: *Kernel* → *Restart*.
4. Verify the package is in your environment: `pip list | grep <package_name>`.

### Plotting Issues

#### Plots not showing inline

**Symptoms:** Code runs but no plot appears in the notebook.

**Solutions:**
1. Ensure `%matplotlib inline` is in the setup cell and has been executed (it's in cell 1).
2. Verify `import matplotlib.pyplot as plt` is run before plotting.
3. Confirm matplotlib backend is set: `%matplotlib inline` should precede all plotting commands.
4. For Jupyter Lab, ensure the Lab extensions are up to date: `jupyter labextension list`.

#### "No module named 'datashader'"

**Symptoms:** Datashader cell fails.

**Solutions:**
1. Install datashader: `pip install datashader colorcet`.
2. Restart the kernel.
3. The notebook includes a fallback to Matplotlib hexbin.

#### Plotly charts show as blank boxes

**Symptoms:** Interactive plots don't render.

**Solutions:**
1. Check browser console (F12) for JavaScript errors.
2. Ensure JavaScript is enabled in your browser.
3. Plotly requires an internet connection (CDN mode) unless you specify a local mode.
4. Try exporting to HTML: the notebook handles this automatically.

### Export Issues

#### "nbconvert: command not found"

**Symptoms:** `jupyter nbconvert --to pdf ...` fails.

**Solutions:**
1. Ensure nbconvert is installed: `pip install nbconvert`.
2. Verify you're in the virtual environment.
3. Use the full path: `/path/to/.venv/bin/jupyter nbconvert ...`.

#### PDF export fails with LaTeX errors

**Symptoms:** `jupyter nbconvert --to pdf` produces errors like "xelatex not found."

**Solutions:**
1. Install LaTeX (see [Installation](./installation.md#latex-for-direct-pdf-export)).
2. Use alternative export methods (HTML + browser print, or Chromium headless).
3. Try `--debug` flag for detailed error messages.

#### Chromium headless produces blank or corrupted PDF

**Symptoms:** PDF is blank, garbled, or partially rendered.

**Solutions:**
1. Verify the HTML file opens correctly in a browser.
2. Check for complex CSS or JavaScript that may not be supported.
3. Try with explicit margins: `--print-to-pdf-margin-top=10`.
4. Upgrade Chromium: `apt update && apt install chromium-browser` (Linux).

### Performance Issues

#### Notebook is very slow

**Symptoms:** Cells take a long time to execute.

**Solutions:**
1. The datashader example creates a large synthetic dataset. Reduce `mult=2000` to a smaller value.
2. Disable inline plotting if not needed (no `%matplotlib inline`).
3. Reduce plot resolution or number of points.
4. Close unused tabs/applications to free system memory.

#### Animation export is very slow

**Symptoms:** `anim.save()` takes minutes or doesn't complete.

**Solutions:**
1. Reduce number of frames: `frames=100` instead of `200`.
2. Use GIF instead of MP4 (simpler encoding).
3. Ensure ffmpeg is properly installed and on PATH.

### Environment Issues

#### Virtual environment not activating

**Symptoms:** `source .venv/bin/activate` doesn't seem to work.

**Solutions:**
1. Verify the venv exists: `ls -la .venv/`.
2. Check shell type: `echo $SHELL`.
3. For bash: `. .venv/bin/activate` (dot-space prefix).
4. For PowerShell (Windows): `.\.venv\Scripts\Activate.ps1`.
5. Check permissions: `chmod +x .venv/bin/activate`.

#### Different Python versions conflicting

**Symptoms:** `python` and `python3` point to different versions; notebooks use the wrong interpreter.

**Solutions:**
1. Always use the venv Python: `which python` should show `.venv/bin/python`.
2. Create venv with explicit version: `python3.10 -m venv .venv`.
3. In Jupyter, select the kernel from the venv: *Kernel* → *Change Kernel*.

## Getting Help

- **Jupyter docs:** [jupyter.readthedocs.io](https://jupyter.readthedocs.io/)
- **Matplotlib FAQ:** [matplotlib.org/faq](https://matplotlib.org/stable/api/faq.html)
- **Seaborn:** [seaborn.pydata.org](https://seaborn.pydata.org/)
- **Plotly:** [plotly.com](https://plotly.com/python/)
- **GitHub Issues:** Report bugs to respective library repositories.

## Still Stuck?

1. Check error messages carefully; they often suggest the fix.
2. Search the library's documentation for your specific error.
3. Search GitHub issues for similar problems.
4. Consider running a fresh venv and re-installing all packages.

Good luck!
