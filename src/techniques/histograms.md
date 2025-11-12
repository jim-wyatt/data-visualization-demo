# Histograms & KDE

## Purpose

Histograms and kernel density estimation (KDE) show the distribution of a single continuous variable. They help identify:
- Central tendency (mode, median).
- Spread and skewness.
- Presence of multiple modes or outliers.

## Example in the Notebook

The notebook plots the distribution of **total bill** from the tips dataset:
- Histogram with 30 bins.
- Overlaid KDE curve.
- Normalized to density (area under curve = 1).

## Key Code Snippet

```python
sns.histplot(tips['total_bill'], bins=30, kde=True, stat='density', ax=ax, color='C2')
ax.set_title('Distribution of total bill (tips dataset)')
```

## Customization Tips

- **Bin count:** Increase `bins=30` for more detail or decrease for a smoother view.
- **Stat type:** Use `stat='count'` for raw counts, `stat='density'` for normalized density, or `stat='percent'`.
- **KDE bandwidth:** Control smoothing with `kde=True` or fine-tune via `hue` and Seaborn's `bw_adjust`.
- **Multiple groups:** Use `hue='day'` to overlay distributions by category.
- **Stacking:** Set `multiple='stack'` or `multiple='dodge'` for grouped histograms.

## When to Use

- **Always:** for exploring univariate distributions.
- **Consider:** KDE for smooth, continuous estimates.
- **Avoid:** histograms for very small samples (< 20 observations).

## See Also

- Seaborn: [histplot()](https://seaborn.pydata.org/generated/seaborn.histplot.html)
- Matplotlib: [hist()](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.hist.html)
