---
layout: post
title: 3D surface of Function
category: Program
author: Guo-Hua Wang
tags: [program]
---

![Figure_2_2](..\2Fundamentals of unconstrained optimization\Figure_2_2.png)

$$
f(x)=8x_1+12x_2+x_1^2-2x_2^2
$$

This function comes from exercise 2.2. The problem asks for the contour lines of function, while I draw 3D surface instead.

Below are codes

 
```python
from matplotlib import pyplot as plt
import numpy as np
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure()
ax = Axes3D(fig)
X = np.arange(-10, 10, 0.5)
Y = np.arange(-10, 10, 0.5)
X, Y = np.meshgrid(X, Y)
Z = 8 * X + 12 * Y + X ** 2 - 2 * Y ** 2

ax.plot_surface(X, Y, Z, rstride=1, cstride=1, cmap='rainbow')
plt.show()
```

