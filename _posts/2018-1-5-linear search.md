---
layout: post
title: steepest descent method
category: program
author: Guo-Hua Wang
tags: [program]
---

![rb](..\2Fundamentals of unconstrained optimization\rb.png)



This is Rosenbrock function which is:
$$
f(x)= 100(x_2-x_1^2)^2+(1-x_1)^2
$$
It's easily to get the minimum is $$(1,1)^T$$. Notice that the first part's weight is 100 which larger than the second part's. So if $$x_2=x_1^2$$, the function value is small.

Here are codes which implement steepest  descent method

```python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# define rosenbrock function
# f(x) = 100(x2 - x1^2)^2 + (1-x1)^2
def f(x):
    return 100*(x[1] - x[0] ** 2) ** 2 + (1 - x[0]) ** 2

def nabla_f(x):
    nabla_f1 = 400 * x[0] ** 3 - 400 * x[0] * x[1] - 2 + 2 * x[0]
    nabla_f2 = 200 * (x[1] - x[0] ** 2)
    result = np.array([nabla_f1, nabla_f2])
    return result

def steepestDescent(nabla_f, nabla2_f, x):
    return - nabla_f(x)

def linearSearch(f, nabla_f, nabla2_f, x0, a0, get_search_direction):
    print(x0, f(x0))
    nodelist = np.hstack([x0, f(x0)])
    x = x0
    a = a0
    count = 10
    while count > 0:
        count = count - 1
        p = get_search_direction(nabla_f, nabla2_f, x)
        if p.all() == 0:
            break
        x = x + a * p
        print(x, f(x))
        nodelist = np.vstack([nodelist, np.hstack([x, f(x)])])
    return nodelist

x0 = np.array([1.2, 1.2])

pointlist = linearSearch(f, nabla_f, nabla_f, x0, 0.0027, steepestDescent)

x0list = pointlist[:, 0]
x1list = pointlist[:, 1]
flist = pointlist[:, 2]
fig = plt.figure()
ax = Axes3D(fig)
X = np.arange(x0list.min()-0.1, x0list.max()+0.1, 0.1)
Y = np.arange(x1list.min()-0.1, x1list.max()+0.1, 0.1)
X, Y = np.meshgrid(X, Y)
Z = f([X, Y])
ax.plot_surface(X, Y, Z, rstride=1, cstride=1, cmap='rainbow')

plt.plot(x0list, x1list, flist, 'ko')
plt.show()
```

set a is 0.001

![rb001](..\2Fundamentals of unconstrained optimization\rb001.png)

set a is 0.002

![rb002](..\2Fundamentals of unconstrained optimization\rb002.png)

set a is 0.0025

![rb0025](..\2Fundamentals of unconstrained optimization\rb0025.png)

set a is 0.0027

![rb0027](..\2Fundamentals of unconstrained optimization\rb0027.png)

set a is 0.0028

![rb0028](..\2Fundamentals of unconstrained optimization\rb0028.png)

set a is 0.003

![rb003](..\2Fundamentals of unconstrained optimization\rb003.png)

