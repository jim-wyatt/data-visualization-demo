# Scatter Plots & Regression

## Purpose

Scatter plots reveal relationships between two continuous variables. Adding a regression line or smoothed curve helps identify trends and fit patterns.

## Example in the Notebook

The notebook uses the **iris dataset** to plot:
1. Sepal length vs. sepal width as a scatter plot, colored and styled by species.
2. A LOWESS (Locally Weighted Scatterplot Smoothing) regression curve overlay.

## Key Code Snippet

```python
sns.scatterplot(data=iris, x='sepal_length', y='sepal_width', hue='species', style='species', ax=ax, s=60)
sns.regplot(data=iris, x='sepal_length', y='sepal_width', scatter=False, ax=ax, 
            color='gray', lowess=True)
```

## Customization Tips

- **Point size:** Change `s=60` to adjust marker size.
- **Regression method:** Use `lowess=True` for non-parametric smoothing or omit for linear regression.
- **Color palettes:** Customize the `hue` palette with `palette='Set2'` or others.
- **Transparency:** Add `alpha=0.6` to scatter points for overlapping data visibility.
- **Faceting:** Use `sns.relplot(..., col='species')` to create subplots per category.

## When to Use

- **Always:** for exploring correlations between two continuous variables.
- **Consider:** adding transparency or jitter when points overlap heavily.
- **Avoid:** when you have too many points (>10,000) without aggregation; use hexbin or datashader instead.

## See Also

- Seaborn: [scatterplot()](https://seaborn.pydata.org/generated/seaborn.scatterplot.html), [regplot()](https://seaborn.pydata.org/generated/seaborn.regplot.html)
- Matplotlib: [scatter()](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.scatter.html)
