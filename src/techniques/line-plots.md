# Line Plots & Time Series

## Purpose

Line plots are ideal for showing trends over time or continuous sequences. They're particularly effective for:
- Time series data (stock prices, temperature, passenger counts).
- Showing changes and trends across ordered categories.
- Comparing multiple time series on the same axes.

## Example in the Notebook

The notebook uses the **flights dataset** to demonstrate:
1. Raw monthly passenger counts as a line.
2. A 12-month rolling average (smoothed trend).
3. Confidence bands (rolling mean ± standard deviation).

## Key Code Snippet

```python
ts = fl.set_index('date')['passengers'].sort_index()
ax.plot(ts.index, ts.values, label='passengers', color='C0')
rolling = ts.rolling(window=12).mean()
ax.plot(rolling.index, rolling.values, label='12-month rolling mean', color='C1')
ax.fill_between(ts.index, (rolling - rolling_std).values, (rolling + rolling_std).values, 
                color='C1', alpha=0.2)
```

## Customization Tips

- **Adjust rolling window:** Change `window=12` to a different period (e.g., 6 for half-yearly).
- **Confidence levels:** Modify the band width (e.g., use 2× standard deviation for ~95% CI).
- **Multiple series:** Plot multiple lines on the same axes with different colors and labels.
- **Markers:** Add `marker='o'` to `ax.plot()` to show data points.

## When to Use

- **Always:** for time-indexed data.
- **Consider:** when you have many repeated measurements and want to show a trend.
- **Avoid:** for categorical data without a natural order (use bar plots instead).

## See Also

- Matplotlib documentation: [plt.plot()](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html)
- Pandas rolling: [Series.rolling()](https://pandas.pydata.org/docs/reference/api/pandas.Series.rolling.html)
