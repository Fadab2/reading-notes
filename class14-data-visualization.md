# Data Visualization

<br />

## Matplotlib tutorial
* Matplotlib is the most used Python package for 2D-graphics.
* IPython is an inhanced Pythonshell with many features including shell commands and allows interactive matplotlib sessions with matplotlib like functionality.
* Pyplot provides a convenient interface to the matplotlib.
* plot sine and cosine: 
```
import numpy as np

X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
C, S = np.cos(X), np.sin(X)
```
* to change colors and line width:
```
plt.figure(figsize=(10,6), dpi=80)
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")
```
* to set limits:

```
plt.xlim(X.min()*1.1, X.max()*1.1)
plt.ylim(C.min()*1.1, C.max()*1.1)
```
* Show to ticks on the x axis:
```
plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi])
plt.yticks([-1, 0, +1])
```
* Showing tick labels "pi" etc:
```
plt.xticks([-np.pi, -np.pi/2, 0, np.pi/2, np.pi],
       [r'$-\pi$', r'$-\pi/2$', r'$0$', r'$+\pi/2$', r'$+\pi$'])

plt.yticks([-1, 0, +1],
       [r'$-1$', r'$0$', r'$+1$'])
```
## Seaborn
* Seaborn is a ploting/data visualization tool.
* Mostly, seaborn uses a set of plotting functions
* There different modules of Seaborn
* Figure-level functions such as `displot` interface with matplotlib through a seaborn object.
* Axes-level functions which add labels and legends to the axis act like drop-in replacements for matplotlib functions and they call the matplotlib.pyplot.gca()
```
f, axs = plt.subplots(1, 2, figsize=(8, 4), gridspec_kw=dict(width_ratios=[4, 3]))
sns.scatterplot(data=penguins, x="flipper_length_mm", y="bill_length_mm", hue="species", ax=axs[0])
sns.histplot(data=penguins, x="species", hue="species", shrink=.8, alpha=.8, legend=False, ax=axs[1])
f.tight_layout()
```

<br />

## References:

[Matplotlib tutorial](https://github.com/rougier/matplotlib-tutorial)

[Seabor](https://seaborn.pydata.org/tutorial/function_overview.html)


<br />

## [<-- Back](README.md)