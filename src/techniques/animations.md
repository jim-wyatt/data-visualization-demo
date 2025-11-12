# Animations

## Purpose

Animations bring data to life by showing changes over time or through parameter space. They're useful for:
- Illustrating temporal evolution.
- Demonstrating algorithm convergence.
- Creating engaging presentations or educational content.

## Example in the Notebook

The notebook uses Matplotlib's **FuncAnimation** to create a simple animated sine wave:
1. The wave oscillates horizontally.
2. The animation runs for 200 frames at 30 ms per frame.
3. It's displayed inline as HTML/JavaScript in the notebook.
4. It's also exported to MP4 (with ffmpeg) or GIF (with Pillow).

## Key Code Snippet

```python
from matplotlib import animation

fig, ax = plt.subplots()
x = np.linspace(0, 2*np.pi, 400)
line, = ax.plot(x, np.sin(x))
ax.set_ylim(-1.5, 1.5)

def init():
    line.set_ydata(np.sin(x))
    return (line,)

def animate(i):
    line.set_ydata(np.sin(x + i/10.0))
    return (line,)

anim = animation.FuncAnimation(fig, animate, init_func=init, frames=200, interval=30, blit=True)
```

## Export Options

- **Inline (Jupyter):** Display directly with `HTML(anim.to_jshtml())` (no external files).
- **MP4:** Requires ffmpeg. Use `anim.save('out.mp4', writer='ffmpeg', fps=30)`.
- **GIF:** Requires Pillow. Use `anim.save('out.gif', writer='pillow', fps=30)`.

## Customization Tips

- **Frame count:** Increase `frames=200` for longer animations.
- **Speed:** Adjust `interval=30` (milliseconds between frames; smaller = faster).
- **Blit mode:** Set `blit=True` for faster rendering (only redraws changed elements).
- **Complex animations:** Use `update_lines_and_patches()` or custom update functions.
- **Interactivity:** Combine with Jupyter widgets (`ipywidgets`) for interactive parameter control.

## When to Use

- **Always:** for time-series visualizations and pedagogical content.
- **Consider:** GIF for social media sharing (MP4 may have compatibility issues on some platforms).
- **Avoid:** animations for static reports (use stills or summaries instead).

## See Also

- Matplotlib: [FuncAnimation](https://matplotlib.org/stable/api/animation_api.html)
- Examples: [matplotlib.org/gallery/animation/](https://matplotlib.org/stable/gallery/index.html#animation)
