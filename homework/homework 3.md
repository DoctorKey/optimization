# homework 3

## Q1

given the nonlinear programming problem:
$$
\min \left(x_1-\frac94\right)^2+\left(x_2-2\right)^2\\
s.t. \space\space\space\space -x_1^2+x_2\geq0\\
x_1+x_2\leq6\\
x_1,x_2\geq0
$$
figure out are those points the optimal solution:
$$
x^{(1)}=\left(\frac32,\frac94\right)^T, x^{(2)}=\left(\frac94,2\right)^T,x^{(3)}=(0,2)^T
$$

## answer

Define:
$$
L(x)=\left(x_1-\frac94\right)^2+\left(x_2-2\right)^2-\lambda_1(-x_1^2+x_2)-\lambda_2(6-x_1-x_2)-\lambda_3x_1-\lambda_4x_2
$$
Then we get:
$$
\nabla_x L(x)=\left[\begin{array}{c}(2+2\lambda_1)x_1-\frac92+\lambda_2-\lambda_3\\2x_2-4-\lambda_1+\lambda_2-\lambda_4\end{array}\right]
$$

$$
\nabla_{xx} L(x)=\left[\begin{array}{cc}2+2\lambda_1&0\\0&2\end{array}\right]
$$

1. $x^{(1)}=\left(\frac32,\frac94\right)^T$, infer $\lambda_1\neq0$, from $\nabla_xL(x^{(1)})=0$, we get $\lambda_2=1/2\gt0$. So $x^{(1)}$ is the optimal solution.
2. $x^{(2)}$ is the optimal solution whose reason is similar to $x^{(1)}$.
3. $x^{(1)}=\left(0,2\right)^T$, infer $\lambda_3\neq0$, from  $\nabla_xL(x^{(3)})=0$, we get $\lambda_3=-9/2\lt0$. So $x^{(3)}$ isn't the optimal solution.

## Q2

Think the nonlinear programming problem:
$$
\max x_1x_2x_3\\
s.t.\space\space\space\space x_1+x_2+x_3=1
$$

1. compute all the points satisfied the KKT condition.
2. among the points in 1, figure out which are local maximum point. Why?

## answer

1. Define:

$$
L(x)=-x_1x_2x_3-\lambda(1-x_1-x_2-x_3)
$$

Then
$$
\nabla_x L(x)=\left[\begin{array}{c}-x_2x_3+\lambda\\-x_1x_3+\lambda\\-x_1x_2+\lambda\end{array}\right]
$$

$$
\nabla_{xx}L(x)=\left[\begin{array}{ccc}0&-x_3&-x_2\\-x_3&0&-x_1\\-x_2&-x_1&0\end{array}\right]
$$

With $\nabla_xL(x)=0$, there are many situations.

* if $\lambda\neq0$, then $x_1=x_2=x_3=1/3$

- if $\lambda=0$, then $x_1=1,x_2=x_3=0$ or $x_2=1,x_1=x_3=0$ or $x_3=1,x_1=x_2=0$.

2. we get $\nabla_xf(x)=\left[\begin{array}{c}-x_2x_3\\-x_1x_3\\-x_1x_2\end{array}\right]$.
   * if $x_1=x_2=x_3=1/3$, then $\nabla_xf(x)=(-1/9,-1/9,-1/9)^T$, So $\nexists w\neq0\space s.t. \space w^T\nabla_xf(x)=0$. Then $x=(1/3,1/3,1/3)^T$ is local maximum point.
   * if $\lambda=0$, we choose $x=(1,0,0)^T$ for example. Because of $\nabla_xf(x)=(0,0,0)^T$, so let $w=(0,w_2,w_3)^T$ which satisfied $w^T\nabla_xf(x)=0$. And $\nabla_{xx}L(x)=\left[\begin{array}{ccc}0&0&0\\0&0&-1\\0&-1&0\end{array}\right]$, then $w^T\nabla_{xx}L(x)w=-2w_2w_3$ which can't make sure it's larger than 0. So these points aren't local maximum points.

## Q3

