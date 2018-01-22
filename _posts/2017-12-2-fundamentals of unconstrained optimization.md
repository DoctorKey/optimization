---
layout: post
title: Fundamental of Unonstrained Optimization
category: BookExercise
author: Guo-Hua Wang
tags: [exercise]
---

## 2.1

for $$f(x) = 100(x_2-x_1^2)^2+(1-x_1)^2$$

$$
\nabla f(x)=\left[\begin{array}{c}200(x_2-x_1^2)*(-2x_1)+2(1-x_1)*(-1)\\
200(x_2-x_1^2)\end{array}\right]\\
=\left[\begin{array}{c}400x_1^3-400x_1x_2+2x_1-2\\
200x_2-200x_1^2\end{array}\right]
$$

$$
\nabla^2 f(x)=\left[\begin{array}{cc}1200x_1^2-400x_2+2&-400x_1\\
-400x_1&200\end{array}\right]
$$

if $$x^*=(1,1)^T$$, then:

$$
\nabla f(x^*)=\left[\begin{array}{c}0\\
0\end{array}\right] \space \space \space \space 
\nabla^2 f(x^*)=\left[\begin{array}{cc}802&-400\\
-400&200\end{array}\right]\succ 0
$$

So $$x^*$$ is a local minimizer of this function.

Then we should show there is no other point that can let $$\nabla f(x)$$ equal 0.

Solve $$\nabla f(x)=0$$, from the second part, we get $$x_2 = x_1^2$$. Replace $$x_2$$ for $$x_1$$ in the first part, then we get $$x_1=1$$ so that $$x_2=1$$. So $$x=(1,1)^T$$ is the only solution to this equation and it's the only local minimizer of this function.

## 2.2

For $$f(x) = 8x_1+12x_2+x_1^2-2x_2^2$$

$$
\nabla f(x)=\left[\begin{array}{c}8+2x_1\\
12-4x_2\end{array}\right]
\qquad
\nabla ^2 f(x)=\left[\begin{array}{cc}2&0\\
0&-4\end{array}\right]
$$

Since $$\nabla f(x)=0$$ only has one solution which is $$x^*=(-4,3)^T$$.

For $$\det([2]) = 2>0$$ and $$\det(\nabla^2 f(x))=-8<0$$, there is no maximum or minimum and the only stationary point is a saddle point.

## 2.3

For $$f_1(x)=a^Tx$$, the gradient and hessian are:

$$
\nabla f(x)=a
\qquad
\nabla^2 f(x)=0
$$

For $$f_2(x)=x^TAx$$, the gradient and hessian are:

$$
\nabla f(x) = 2Ax
\qquad
\nabla^2 f(x) = 2A
$$

## 2.4

For (2.6) which is $$f(x+p) = f(x) + \nabla f(x)^T p + \frac12p^T\nabla^2f(x+tp)p$$ for some $$t\in(0,1)$$, we take $$\cos(1/x)$$ as $$f(x)$$ and get second-order expansion:

$$
\cos(1/(x+p)) = cos(1/x) + \frac{\sin(1/(x+tp))p}{x^2} 
$$

We take $$\cos(x)$$ as $$f(x)$$ and get third-order Taylor expansion:

$$
\cos(x) = \cos(0)-\sin(0)x-\frac12\cos(tx)x^2=1-\frac12\cos(tx)x^2
$$

When $$x=1$$, then:

$$
\cos(1)=1-\frac12\cos(t)\qquad for \space some \space t\in(0,1)
$$

## 2.5

With $$f(x)=\|x\|^2$$ and 

$$
x_k=\left(1+\frac1{2^k}\right)\left[\begin{array}{c}\cos k\\\sin k\end{array}\right]
$$

then

$$
f(x_k)=\|\left(1+\frac1{2^k}\right)\left[\begin{array}{c}\cos k\\\sin k\end{array}\right]\|^2=1+\frac1{2^k}
$$

Then

$$
f(x_{k+1})=1+\frac1{2^{k+1}}<1+\frac1{2^k}=f(x_k)
$$

For $$\forall x^*\in\{x\vert\|x\|^2=1\}$$, $$x^*$$ can be expressed by $$x^*=(\cos(\theta^*),\sin(\theta^*))^T$$.  Now we should proof $$x^*$$ is a limit point for $$\{x_k\}$$.

Since $$\theta^*$$ is a limit point of the subsequence $$\{\xi_k\}$$ defined by

$$
\xi_k=k(\mod 2\pi)=k-2\pi\left\lfloor\frac{k}{2\pi}\right\rfloor
$$

$$(\cos(\theta^*),\sin(\theta^*))^T$$ is a limit point of the subsequence $$\{(\cos(\xi_k),\sin(\xi_k))^T\}$$.

For $$\lim_{k\rightarrow\infty}1+\frac{1}{2^k} = 1$$, $$(\cos(\theta^*),\sin(\theta^*))^T$$ is a limit point of the subsequence $$\{(1+\frac{1}{2^k}) (\cos(\xi_k),\sin(\xi_k))^T\}$$. 

Therefore, every point on the unit circle is a limit point for $$\{x_k\}$$. 

## 2.6 

If $$x^*$$ is an isolated local minimizer, there is a neighborhood $$N$$ and $$x^*$$ is the only local minimizer in $$N$$. If there is a $$x'$$ which $$f(x^*)=f(x')$$, $$f(x')=f(x^*)\leq f(x)$$ for $$x\in N$$. So $$x'$$ is a local minimizer which conflict with the condition. So $$\forall x\neq x^*, x\in N$$, $$f(x^*)<f(x)$$. So all isolated local minimizers are strict.

##2.7

$$
f(y+\alpha (x-y))-\alpha f(x)-(1-\alpha)f(y)\\
=(y+\alpha (x-y)^T)Q(y+\alpha (x-y))-\alpha x^TQx-(1-\alpha)y^TQy\\
=\alpha (\alpha-1)(y-x)^TQ(y-x)
$$

For all $$\alpha \in [0,1]$$ and $$Q$$ is a symmetric positive semidefinite matrix, $$\alpha (\alpha-1)(y-x)^TQ(y-x) \leq 0$$. So $$f(x)$$ is convex on the domain $$R^n$$.

## 2.8

Define $$A=\{x\vertf(x)\leq f(t) \quad\forall t \in D\}$$ and $$A$$ is the set of global minimizers of $$f(x)$$.

$$
\forall x_1,x_2\in A \qquad f(x_1)\leq f(t) \qquad f(x_2)\leq f(t)
$$

$$\forall \lambda_1,\lambda_2 \geq0, \lambda_1+\lambda_2=1$$. Since $$f(x)$$ is convex, we get $$\lambda_1 f(x_1)+\lambda_2 f(x_2)\geq f(\lambda_1 x_1+\lambda_2 x_2)$$

Define $$x_3=\lambda_1 x_1 + \lambda_2 x_2$$, then $$f(x_3)\leq \lambda_1 f(x_1)+\lambda_2 f(x_2)\leq \lambda_1 f(t)+ \lambda_2 f(t)=f(t) \quad \forall t\in D$$

So $$x_3\in A$$ and $$A$$ is a convex set.

## 2.9

With $$x=(1,0)^T, p^T=(-1,1)$$, $$x+\alpha p=(1-\alpha,\alpha)^T$$.

With $$f(x_1,x_2)=(x_1+x_2^2)^2$$, $$f(x+\alpha p)=(\alpha^2-\alpha+1)^2$$.

$$\nabla f(x)=\left[\begin{array}{c}2(x_1+x_2^2)\\2(x_1+x_2^2)2x_2\end{array}\right]$$, then $$\nabla f(x) = (2,0)^T$$. So $$p^T\nabla f(x)=-2<0$$ and $$p$$ is a descent direction.

Define $$g(\alpha)=(\alpha^2-\alpha+1)^2$$. We should solve $$\min g(\alpha)$$ when $$\alpha >0$$.

Let $$g(\alpha)'=2(\alpha^2-\alpha+1)(2\alpha-1)=0$$, then we get $$\alpha=1/2$$ which is minimizer of the problem (2.10)

##2.10

$$
\nabla \widetilde{f}(z)=\frac{d \widetilde{f}(z)}{dz_j}=\frac{dx_i}{dz_j}\frac{d\widetilde{f}(z)}{dx_i}=S^T\nabla f(x)
$$

$$
\nabla^2 \widetilde{f}(z)=\frac{d \nabla\widetilde{f}(z)}{dz_j}=\frac{dx_i}{dz_j}\frac{d\nabla \widetilde{f}(z)}{dx_i}=S^T\nabla^2f(x)S
$$

## 2.13

$$\forall \epsilon >0$$, let $$K=1/\epsilon$$, $$\|x_k-0\|=1/k\leq \epsilon$$ for all $$k \geq K$$. So $$x_k$$ converge to zero.

$$
\frac{\|x_{k+1}-x^*\|}{\|x_k-x^*\|}=\frac{k}{k+1}
$$

$$\forall r \in(0,1)$$, let $$k>\frac1{1-r}$$, then $$\frac{k}{k+1}>r$$. So there no $$r \in (0,1)$$ satisfied when $$k >K$$  $$\frac{k}{k+1}<r$$.

So $$x_k$$ is not Q-linearly convergent.

## 2.14

$$
\frac{\|x_{k+1}-x^*\|}{\|x_k-x^*\|^2}=\frac{(0.5)^{2^{k+1}}}{((0.5)^{2^k})^2}=0.5^0=1
$$

## 2.15

easy to get $$x_k\rightarrow 0$$. Then:

$$
\lim_{k\rightarrow \infty} \frac{\|x_{k+1}-x^*\|}{\|x_k-x^*\|}=\frac{\frac1{(k+1)k!}}{\frac1{k!}}=\frac1{k+1}=0
$$

So $$x_k$$ converge Q-superlinearly

## 2.16

easy to get $$x_k\rightarrow 0$$ while $$(\frac14)^{2k}$$ converge Q-quadratically and $$\frac1k$$ converget sublinearly. So $$x_k$$ converge R-quadratically which dominated by $$(\frac14)^{2k}$$.