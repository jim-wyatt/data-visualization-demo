# Datashader for Large Datasets

## Purpose

When you have hundreds of thousands or millions of data points, traditional scatter plots become too slow and visually cluttered. **Datashader** rasterizes and aggregates points into a grid for efficient, artifact-free rendering.

## Use Cases

- Stock tick data (millions of prices per second).
- Sensor readings from IoT devices.
- Geographic data points (billions of GPS coordinates).
- Scientific simulations with dense output.

## Example in the Notebook

The notebook demonstrates datashader by:
1. Creating a synthetic dataset (tips repeated 2000 times with jitter) — ~500k rows.
2. Aggregating points into a canvas grid.
3. Shading the grid by point count using a colormap.
4. Falling back to Matplotlib hexbin if datashader is unavailable.

## Key Code Snippet

```python
import datashader as ds
import datashader.transfer_functions as tf

cvs = ds.Canvas(plot_width=800, plot_height=400)
agg = cvs.points(big, 'x', 'y', ds.count())
img = tf.shade(agg, cmap=colorcet.m_fire, how='eq_hist')
```

## Customization Tips

- **Canvas size:** Adjust `plot_width` and `plot_height` for resolution.
- **Aggregation:** Use `ds.count()` (default), `ds.mean()`, `ds.sum()`, or custom reductions.
- **Colormaps:** Choose from `colorcet` library (perceptually uniform): `m_fire`, `m_viridis`, etc.
- **Normalization:** Use `how='eq_hist'` for histogram equalization or `how='linear'` for simple scaling.
- **Fallback:** The notebook includes a `sns.hexbin()` fallback if datashader is not installed.

## Installation

If datashader is not in your environment:

```bash
pip install datashader colorcet
```

## When to Use

- **Always:** for datasets with >100k points.
- **Consider:** for exploratory analysis of massive datasets.
- **Avoid:** if you need individual point interactivity (use aggregated tooltips instead).

## See Also

- Datashader: [datashader.org](http://datashader.org/)
- Colorcet: [colorcet library](https://colorcet.holoviz.org/)
