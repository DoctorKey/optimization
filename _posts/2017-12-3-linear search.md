---
layout: post
title: Line Search Methods
category: BookExercise
author: Guo-Hua Wang
tags: [exercise]
---

### 3.2

$$\Phi (\alpha)=f(x_k+\alpha p_k)$$ is bounded below for all $$\alpha > 0$$. Since $$0<c_1<1$$ the line $$l(\alpha)=f(x_k)+\alpha c_1\nabla f_k^Tp_k$$ is unbounded below and must therefore intersect the graph of $$\Phi$$ at least one. Suppose they intersect only once which means $$\Phi(\alpha)>l(\alpha)\quad \alpha > \alpha '$$ . Then we should proof when $$0<\alpha < \alpha '$$   ,$$\Phi'(\alpha) < c_2\nabla f_k^Tp_k$$.

Define $$g(\alpha) = c_2 \nabla f_k^T p_k-\Phi'(\alpha)$$. Therefore:

$$
g(0)=c_2\nabla f_k^T p_k-\Phi'(0)=(c_2-1)\nabla f_k^T p_k>0
$$

and $$g'(\alpha)=-\Phi''(\alpha)=-p_k^T\nabla^2f_k^T p_k$$. Then if $$g'(\alpha) > 0$$, $$g(\alpha)>0$$. So when $$0<\alpha < \alpha '$$ ,  $$\Phi'(\alpha) < c_2\nabla f_k^Tp_k$$.

### 3.3

For $$f(x)=\frac12x^TQx-b^Tx$$, we have:

$$
f(x_k+\alpha p_k)=\frac12(x_k+\alpha p_k)^TQ(x_k+\alpha p_k)-b^T(x_k+\alpha p_k)\\
=f(x_k)+\frac12\alpha_k^2p_k^TQp_k+\alpha p_k^TQx_k-\alpha b^Tp_k\\
=f(x_k)+\frac12\alpha_k^2p_k^TQp_k+\alpha \nabla f_k^Tp_k
$$

then:

$$
\frac{\partial f(x_k+\alpha p_k)}{\partial \alpha}=\alpha p_k^TQp_k + \nabla f_k^T p_k
$$

When the above expression equal 0, we obtain $$\alpha = -\frac{\nabla f_k^T p_k}{p_k^T Q p_k}$$

### 3.4

As the above problem show:

$$
f(x_k+\alpha p_k)=f(x_k)+\frac12\alpha_k^2p_k^TQp_k+\alpha \nabla f_k^Tp_k\\
=f(x_k)+\frac{(\nabla f_k^Tp_k)^2}{2p_k^TQp_k}-\frac{(\nabla f_k^Tp_k)^2}{p_k^TQp_k}\\
=f(x_k)-\frac{(\nabla f_k^Tp_k)^2}{2p_k^TQp_k}\\
=f(x_k)+\frac12\alpha \nabla f_k^Tp_k
$$

For $$\alpha_k \nabla f_k^T p_k < 0$$, we obtain

$$
f(x_k)+(1-c)\alpha_k \nabla f_k^Tp_k\leq f(x_k+\alpha p_k)\leq f(x_k)+c\alpha_k \nabla f_k^T p_k \qquad 0<c<\frac12
$$

### 3.5


$$
\|B^{-1}\|\|Bx\|\geq \|B^{-1}Bx\|=\|x\|
$$

$$
\cos \theta_k=-\frac{\nabla f_k^T p_k}{\|\nabla f_k\|\|p_k\|} = \frac{\nabla f_k^T B_k^{-1}\nabla f_k}{\|\nabla f_k\|\|-B_k^{-1}\nabla f_k\|}\\
\geq\frac{\|\nabla f_k\|}{\|\nabla f_k\|\|B_k^{-1}\nabla f_k\|\|(B_k^{-1}\nabla f_k)^{-1}\|}\\
=\frac{1}{\|B_k^{-1}\|\|B_k\|}\geq \frac{1}{M}
$$

### 3.6

