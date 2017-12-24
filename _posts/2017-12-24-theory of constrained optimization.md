---
layout: post
title: Conjugate Gradient Methods
category: BookExercise
author: Guo-Hua Wang
tags: [exercise]
---

###12.1

####(a)

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

####(b)

$$\forall k$$, let $$x=\frac{1}{k\pi}$$, then $$\exists N=\left(\frac{1}{(k+1) \pi },\frac{1}{(k-1) \pi }\right) $$. $$x$$ is the only feasible point in $$N$$

####(c)

Let $$x=\frac{1}{k\pi}$$ and $$f(x)=\frac{1}{k^2\pi^2}>0=f(0)$$. So $$x^*=0$$ is a global solution. Then it's a strict local solution. $$\forall \delta>0$$, $$x^*\in(-\delta,\delta)$$, let $$k>\frac{1}{\delta\pi}$$, then $$x=\frac{1}{k\pi}<\delta$$ and $$x\in(-\delta,\delta)$$. So $$x$$ is a local solution. So $$x^*$$ isn't an isolated local solution.