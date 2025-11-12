# Heatmaps & Correlations

## Purpose

Heatmaps visualize two-dimensional data (matrices) using color intensity. Common uses:
- Correlation matrices (how variables relate).
- Confusion matrices (classification performance).
- Time-series aggregations (e.g., activity by hour and day).

## Example in the Notebook

The notebook computes and displays the **correlation matrix of iris features**:
- Sepal length, sepal width, petal length, petal width.
- Uses a diverging color palette (coolwarm) centered at 0.
- Annotations show exact correlation values.

## Key Code Snippet

```python
corr = iris.select_dtypes(include=np.number).corr()
sns.heatmap(corr, annot=True, cmap='coolwarm', center=0, ax=ax)
```

## Customization Tips

- **Color map:** Use `cmap='viridis'` (perceptually uniform), `cmap='RdBu_r'` (diverging), or `cmap='Greens'` (sequential).
- **Annotation:** Set `annot=True` to show values, or `annot=False` to hide.
- **Centering:** Use `center=0` for diverging colormaps to anchor at a meaningful value.
- **Normalization:** Use `vmin` and `vmax` to control the color scale range.
- **Clustermap:** Use `sns.clustermap()` to hierarchically cluster rows/columns.

## When to Use

- **Always:** for visualizing correlations and matrices.
- **Consider:** clustering when you want to identify related variables/samples.
- **Avoid:** heatmaps for more than ~20×20 cells without annotation clarity.

## See Also

- Seaborn: [heatmap()](https://seaborn.pydata.org/generated/seaborn.heatmap.html), [clustermap()](https://seaborn.pydata.org/generated/seaborn.clustermap.html)
- Matplotlib: [imshow()](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.imshow.html)
