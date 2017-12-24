---
layout: post
title: Theory of Constrained Optimization
category: BookExercise
author: Guo-Hua Wang
tags: [exercise]
---

### 12.1

#### (a)

$$
\lim_{x\rightarrow 0+} c(x)=\lim_{x\rightarrow 0+} x^6\sin{\frac 1x} = 0
$$

$$
c'(x)=6x^5\sin{\frac 1x}+\cos\frac 1x(-\frac{1}{x^2})x^6=6x^5\sin\frac 1x-x^4\cos \frac 1x
$$

$$
\lim_{x\rightarrow 0^+} c'(x)=0
$$

$$
c''(x)=30x^4\sin \frac1x-x^2\sin \frac 1x-6x^3\cos \frac1x-4x^3\cos\frac 1x
$$

$$
\lim_{x\rightarrow 0^+}c''(x)=0
$$

So the constraint function is twice continuously differentiable at all x.

Force $$c(x)=0$$, then we get:

1. If $$x=0$$, $$c(x)=0$$
2. If $$x\neq 0$$, $$x^6\sin\frac1x=0$$ infers $$\sin\frac1x=0$$. So $$x=\frac{1}{k\pi}$$

#### (b)

$$\forall k$$, let $$x=\frac{1}{k\pi}$$, then $$\exists N=\left(\frac{1}{(k+1) \pi },\frac{1}{(k-1) \pi }\right) $$. $$x$$ is the only feasible point in $$N$$

#### (c)

Let $$x=\frac{1}{k\pi}$$ and $$f(x)=\frac{1}{k^2\pi^2}>0=f(0)$$. So $$x^*=0$$ is a global solution. Then it's a strict local solution. $$\forall \delta>0$$, $$x^*\in(-\delta,\delta)$$, let $$k>\frac{1}{\delta\pi}$$, then $$x=\frac{1}{k\pi}<\delta$$ and $$x\in(-\delta,\delta)$$. So $$x$$ is a local solution. So $$x^*$$ isn't an isolated local solution.

### 12.2

If $$x^*$$ is isolated local solution, $$\exists N, x\in N$$ and $$x$$ is the only local solution in $$N\cap \Omega$$. i.e. $$f(x)\geq f(x^*)\quad \forall x \in N$$. Suppose $$\exists x'\in N , x'\neq x$$ s.t. $$f(x')=f(x^*)$$. Then $$f(x)\geq f(x^*)=f(x')\quad\forall x \in N$$. $$x'$$ is a local solution which conflict with $$x^*$$ is isolated local solution. So $$\forall x \in N, x\neq x^*$$,$$f(x)\leq f(x^*)$$. Then $$x^*$$ is strict local solution.

### 12.4*

Take any local solution denoted by $$x_0$$. This means that there exists a neighborhood $$N(x_0)$$ such that $$f(x_0)\leq f(x)$$ holds for any $$x\in N(x_0)\cap \Omega$$. The following proof is based on contradiction.

Suppose $$x_0$$ is not a global solution, then we take a global solution $$\tilde{x} \in \Omega$$, which satisfies $$f(x_0)>f(\tilde{x})$$. Because $$\Omega$$ is a convex set, there exists $$\alpha \in [0,1]$$ such that $$\alpha x_0+(1-\alpha)\tilde{x}\in N(x_0)\cap \Omega$$. Then the convexity of $$f(x)$$ gives 

$$
\begin{align}
f(\alpha x_0+(1-\alpha)\tilde{x})&\leq \alpha f(x_0)+(1-\alpha)f(\tilde{x})\\
&< \alpha f(x_0)+(1-\alpha)f(x_0)\\
&=f(x_0)
\end{align}
$$

which contradicts the fact that $$x_0$$ is the minimum point in $$N(x_0)\cap \Omega$$. It follows that $$x_0$$ must be a global solution.

Now, let us prove that the set of global solutions is convex. Let

$$
S=\{x| x\space is \space a\space global \space solution \space to \space problem\}
$$

and consider any $$x_1,x_2\in S$$ such that $$x_1\neq x_2$$ and $$x_3=\alpha x_1+(1-\alpha)x_2$$, $$\alpha\in (0,1)$$. By the convexity of $$f(x)$$ which is $$f(x_1) \leq f(x)$$ and $$f(x_2)\leq f(x)$$ for any $$x\in \Omega$$, we have

$$
\begin{align}
f(x_3)&=f(\alpha x_1+(1-\alpha)x_2)\\
&\leq \alpha f(x_1)+(1-\alpha)f(x_2)\\
&\leq \alpha f(x)+(1-\alpha)f(x)\\
&=f(x)
\end{align}
$$

So $$x_3$$ is a global solution. Therefore, $$S$$ is a convex set.

### 12.5*

Recall

$$
\begin{align}
f(x)&=\|v(x)\|_{\infty}\\
&=\max|v_i(x)|, i=1,\dots,m.
\end{align}
$$

Minimizing $$f$$ is equivalent to minimizing $$t$$ where $$ |v_i(x)| \leq t, i=1,\dots,m$$. i.e., the problem can be reformulated as

$$
\begin{align}
&\min_x t&\\
s.t.\quad& t-v_i(x)\geq 0, i=1,\dots,m\\
& t+v_i(x)\geq0, i=1,\dots,m
\end{align}
$$

Similarly, for $$f(x)=\max v_i(x),i=1,\dots,m.$$ the minimization problem can be reformulated as

$$
\begin{align}
&\min_x t\\
s.t. \quad& t-v_i(x)\geq0, i=1,\dots,m
\end{align}
$$

### 12.7*

Given

$$
d = -\left(I-\frac{\nabla c_1(x)\nabla c_1^T(x)}{\|\nabla c_1(x)\|^2}\right)\nabla f(x)
$$

we find

$$
\begin{align}
\nabla c_1^T(x)d &= -\nabla c_1^T(x)\left(I-\frac{\nabla c_1(x)\nabla c_1^T(x)}{\|\nabla c_1(x)\|^2}\right)\nabla f(x)\\
&=-\nabla c_1^T(x)\nabla f(x)+\frac{(\nabla c_1^T(x)\nabla c_1(x))(\nabla c_1^T(x)\nabla f(x))}{\|\nabla c_1(x)\|^2}\\
&=0.
\end{align}
$$

Furthermore,

$$
\begin{align}
\nabla f^T(x)d&=-\nabla f^T(x)\left(I-\frac{\nabla c_1(x)\nabla c_1^T(x)}{\|\nabla c_1(x)\|^2}\right)\nabla f(x)\\
&=-\nabla f^T(x)\nabla f(x)+\frac{\nabla f^T(x)\nabla c_1(x)\nabla c_1^T(x)\nabla f(x)}{\|\nabla c_1(x)\|^2}\\
&=-\|\nabla f(x)\|^2+\frac{(\nabla f^T(x)\nabla c_1(x))^2}{\|\nabla c_1(x)\|^2}\\
&=-\|\nabla f(x)\|^2+\frac{\|\nabla f(x)\|^2\|\nabla c_1(x)\|^2\cos^2(\theta)}{\|\nabla c_1(x)\|^2}\\
&=(\cos^2(\theta)-1)\|\nabla f(x)\|^2\\
\end{align}
$$

Since $$\nabla f(x)$$ and $$\nabla c_1(x)$$ are not parallel, $$-1<\cos(\theta) <1$$. So $$\nabla f^T(x)d<0$$

### 12.13*

The constraints can be written as

$$
\begin{align}
c_1(x)&=2-(x_1-1)^2-(x_2-1)^2\geq 0,\\
c_2(x)&=2-(x_1-1)^2-(x_2+1)^2\geq 0,\\
c_3(x)&=x_1\geq 0,
\end{align}
$$

So

$$
\nabla c_1(x)=\left[
\begin{array}{c}
-2(x_1-1)\\
-2(x_2-1)
\end{array}
\right],
\nabla c_2(x)=\left[
\begin{array}{c}
-2(x_1-1)\\
-2(x_2+1)
\end{array}
\right],
\nabla c_3(x)=\left[
\begin{array}{c}
1\\
0
\end{array}
\right],
$$

​All constraints are active at $$x^*=(0,0)$$. The number of active constraints is three, but the dimension of the problem is only two, so $$ \{\nabla c_i | i\in A(x^*)\} $$ is not a linearly independent set and LICQ does not hold. However, for $$w=(1,0)$$, $$\nabla c_i(x^*)^Tw>0$$ for all $$i\in A(x^*)$$, so MFCQ does hold.

### 12.14*

The optimization problem can be formulated as

$$
\min_x f(x)=\|x\|^2\\
s.t. \quad c(x)=a^Tx+\alpha \geq 0.
$$

The Lagrangian function is

$$
L(x,\lambda)=f(x)-\lambda c(x)=\|x\|^2-\lambda(\alpha^Tx+\alpha)
$$

and its derivatives are

$$
\nabla_x L(x,\lambda)=2x-\lambda a\\
\nabla_{xx} L(x,\lambda)=2I
$$

Notice that the second order sufficient condition $$\nabla_{xx}L(x,\lambda)=2I>0$$ is satisfied at all points.

The KKT conditions $$\nabla_x L(x^*,\lambda^*)=0$$, $$\lambda^*c(x^*)=0$$, $$\lambda^*\geq 0$$ imply

$$
x^*=\frac{\lambda^*}{2}a
$$

and

$$
\lambda^*=0 \space or \space a^Tx^*+\alpha=\frac{\lambda^*\|a\|^2}{2}+\alpha=0
$$

There are two cases. First, if $$\alpha \geq 0$$, then the latter condition implies $$\lambda^*=0$$, so the solution is $$(x^*,\lambda^*)=(0,0)$$. Second, if $$\alpha <0$$, then

$$
(x^*,\lambda^*)=-\left(\frac{\alpha}{\|a\|^2}a,\frac{2}{\|a\|^2}\right)
$$

### 12.16*

Eliminating the $$x_2$$ variable yields

$$
x_2=\pm \sqrt{1-x_1^2}
$$

There are two cases:

**Case 1:** Let $$x_2=\sqrt{1-x_1^2}$$. The optimization problem becomes

$$
\min_{x_1} f(x_1)=x_1+\sqrt{1-x_1^2}
$$

The first order condition is

$$
\nabla f=1-\frac{x_1}{\sqrt{1-x_1^2}}=0
$$

which is satisfied by $$x_1=\pm 1/\sqrt{2}$$. Plugging each into $$f$$ and choosing the value for $$x_1$$ that yields a smaller objective value, we find the solution to be $$(x_1,x_2)=(-1/\sqrt{2},1/\sqrt{2})$$.

**Case 2:** Let $$x_2=-\sqrt{1-x_1^2}$$. The optimization problem becomes

$$
\min_{x_1}f(x_1)=x_1-\sqrt{1-x_1^2}
$$

The first order condition is

$$
\nabla f=1+\frac{x}{\sqrt{1-x_1^2}}=0
$$

which is satisfied by $$x_1=\pm 1/\sqrt{2}$$. Plugging each into $$f$$ and choosing the value for $$x_1$$ that yields a smaller objective value, we find the solution to be $$(x_1,x_2)=(-1/\sqrt{2},-1/\sqrt{2})$$.

Each choice of sign leads to a distinct solution. However, only case 2 yields the optimal solution

$$
x^*=\left(-\frac{1}{\sqrt{2}},-\frac{1}{\sqrt{2}}\right).
$$






##### * means reference from [official answer](https://www.calpoly.edu/~ajjimene/NumericalOptimization-Nocedal-Wright-SolutionsManual.pdf)