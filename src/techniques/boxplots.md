# Box & Violin Plots

## Purpose

Box plots and violin plots compare distributions across groups. They highlight:
- Median and quartiles (box plot).
- Full distribution shape (violin plot).
- Outliers and range.

## Example in the Notebook

The notebook displays **total bill by day** using:
1. A box plot (left panel) — shows median, IQR, whiskers, and outliers.
2. A violin plot (right panel) — shows the full distribution shape.
3. An overlaid swarm plot (right panel) — individual data points.

## Key Code Snippet

```python
sns.boxplot(data=tips, x='day', y='total_bill', hue='day', dodge=False, ax=axes[0], palette='pastel')
sns.violinplot(data=tips, x='day', y='total_bill', hue='day', split=False, inner=None, ax=axes[1], palette='muted')
sns.swarmplot(data=tips, x='day', y='total_bill', color='k', size=3, ax=axes[1])
```

## Customization Tips

- **Boxplot parts:** Show quartiles, mean, or whiskers with `showmeans=True`, `showfliers=True`.
- **Violin plot shape:** Use `split=True` to compare two hue groups side-by-side (for 2-level categorical).
- **Inner representation:** Set `inner='box'`, `inner='quartile'`, or `inner=None` (violin only).
- **Point overlay:** Add `sns.swarmplot()` or `sns.stripplot()` for individual observations.
- **Orient:** Use `orient='h'` for horizontal layout.

## When to Use

- **Box plots:** quick comparison of medians and spreads across many groups.
- **Violin plots:** when distribution shape matters more than individual points.
- **Swarm overlay:** when sample size is small (< 50 per group) and you want to see all points.

## See Also

- Seaborn: [boxplot()](https://seaborn.pydata.org/generated/seaborn.boxplot.html), [violinplot()](https://seaborn.pydata.org/generated/seaborn.violinplot.html), [swarmplot()](https://seaborn.pydata.org/generated/seaborn.swarmplot.html)
