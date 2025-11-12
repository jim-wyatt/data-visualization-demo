# Interactive Plots with Plotly

## Purpose

Interactive plots enable users to explore data dynamically via hover tooltips, zooming, panning, and legend toggling. Plotly is a popular library for building web-based interactive charts.

## Example in the Notebook

The notebook creates two Plotly Express charts:
1. **Scatter plot:** total bill vs. tip, colored by day, with hover data (sex, party size).
2. **Line plot:** monthly passenger counts over time.

Both are exported to HTML files that can be opened in any web browser.

## Key Code Snippet

```python
import plotly.express as px
fig = px.scatter(tips, x='total_bill', y='tip', color='day', 
                 hover_data=['sex', 'size'], title='Tips: total bill vs tip')
fig.write_html('interactive_tips.html', include_plotlyjs='cdn')
```

## Features

- **Hover tooltips:** Show data values and custom labels.
- **Zoom & pan:** Click and drag to zoom; double-click to reset.
- **Legend toggling:** Click legend items to show/hide traces.
- **Download:** Camera icon to save as PNG.
- **Export:** Save as HTML for sharing or embedding in reports.

## Customization Tips

- **Markers:** Change marker size with `size='size'` column or fixed `marker_size=10`.
- **Colors:** Use `color='day'` for categorical or `color_continuous_scale='Viridis'` for continuous.
- **Faceting:** Add `facet_row='day'` or `facet_col='day'` for subplots.
- **Annotations:** Use `fig.add_annotation()` to add text or arrows.
- **Custom styling:** Modify `fig.update_layout()` and `fig.update_traces()`.

## When to Use

- **Always:** for exploratory data analysis and interactive dashboards.
- **Consider:** exporting to HTML for stakeholder sharing (no Python environment needed).
- **Avoid:** Plotly for very large datasets (>50k points) without aggregation; consider datashader instead.

## See Also

- Plotly Express: [scatter()](https://plotly.com/python/scatter-plots/), [line()](https://plotly.com/python/line-charts/)
- Plotly documentation: [plotly.com](https://plotly.com/python/)
