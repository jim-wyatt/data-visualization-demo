# HTML Export + Browser Print

## Overview

This method exports the notebook to HTML (widely supported) and then uses your web browser's Print dialog to save as PDF. It's universal, works everywhere, and gives you control over page setup.

## Step 1: Export to HTML

From the project directory:

```bash
jupyter nbconvert --to html data-visualization-demo.ipynb
```

This creates `data-visualization-demo.html`.

## Step 2: Open in a Browser

Open `data-visualization-demo.html` in your preferred web browser (Chrome, Firefox, Safari, Edge, etc.).

## Step 3: Print to PDF

1. **Open Print dialog:** `Ctrl+P` (Windows/Linux) or `Cmd+P` (macOS).
2. **Configure:**
   - Destination: "Save as PDF" (Chrome/Edge) or "Print to File" (Firefox).
   - Margins: Choose "None" to minimize whitespace.
   - Paper size: A4 or Letter as desired.
   - Background graphics: Check if you want colors (usually on by default).
3. **Save:** Choose a filename and click "Save."

## Advantages

- **No extra software:** Works with any browser.
- **Visual control:** Adjust margins, headers, footers in the Print dialog.
- **Compatibility:** HTML is backward-compatible and future-proof.
- **Responsive:** Modern browsers handle layout well.

## Troubleshooting

**Interactive plots don't appear**
- Plotly and other interactive content render only if JavaScript is enabled in your browser. Check browser console for JS errors.

**Headers/footers in printed PDF**
- Adjust in the Print dialog. Some browsers allow custom headers/footers.

**Page breaks**
- Long notebooks may split awkwardly. Use CSS (custom notebook template) to control page breaks if needed.

## See Also

- Notebook Print Stylesheet: [Jupyter docs](https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Notebook%20Basics.html)
