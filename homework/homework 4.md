# homework 4

## Q1

give the linear programming:
$$
\min z = -x_1-2x_2\\
s.t. -2x_1+x_2\leq2\\
-x_1+2x_2\leq7\\
x_1+2x_2\leq3\\
x_1,x_2\geq0
$$
use the prime-dual interior-point method to iterate once. Suppose $\mu=10$ in the beginning, and the **infeasible** starting guess is:
$$
x = (1,1,1,1,1)^T,y=(0,0,0)^T,s=(1,1,1,1,1)^T
$$

## answer

$$
A=\left(\begin{array}{ccccc}
-2 & 1 & 1 & 0 & 0\\
-1 & 2 & 0 & 1 & 0\\
1 & 2 & 0 & 0 & 1
\end{array}\right)
$$

$$
b=\left(\begin{array}{ccc}2 & 7&3\end{array}\right)^T, 
c=\left(\begin{array}{ccccc}-1 & -2&0&0&0\end{array}\right)^T
$$

$$
X=diag(x)=I_{5\times5}, S=diag(s)=I_{5\times5}
$$

$$
\nu(\mu)=\mu e-XSe=\left(\begin{array}{ccccc}9 & 9&9&9&9\end{array}\right)^T
$$

$$
r_p = b-Ax=\left(\begin{array}{ccc}2 & 5&-1\end{array}\right)^T
$$

$$
r_D=c-A^Ty-s=\left(\begin{array}{ccccc}-2 & -3&-1&-1&-1\end{array}\right)^T
$$

$$
D=S^{-1}X=I_{5\times5}
$$

$$
\Delta y =-(ADA^T)^{-1}[AS^{-1}\nu(\mu)-ADr_D-r_p]=
\left(\begin{array}{ccc}-1 & 2&-\frac{26}{3}\end{array}\right)^T
$$

$$
\Delta s = -A^T\Delta y=\left(\begin{array}{ccccc}20/3 & 34/3&0&-3&23/3\end{array}\right)^T
$$

$$
\Delta x = S^{-1}\nu(\mu)-D\Delta s=\left(\begin{array}{ccccc}7/3 & -7/3&9&12&4/3\end{array}\right)^T
$$

$$
x=x+\Delta x = \left(\begin{array}{ccccc}10/3 & -4/3&10&13&7/3\end{array}\right)^T
$$

$$
y=y+\Delta y = \left(\begin{array}{ccc}-1 & 2&-26/3\end{array}\right)^T
$$

$$
s=s+\Delta s = \left(\begin{array}{ccccc}23/3 & 37/3&1&-2&26/3\end{array}\right)^T
$$

## Q2

think the optimal problem:
$$
\min \frac12||x||^2\\
s.t. a^Tx=b\\
x\geq0
$$
for $a\in R^n$,$a\geq0$ and $b\in R$, $b>0$. Try to explain if this problem has the optimal solution, then the optimal solution is uniform and use a and b to express the optimal solution.

## answer

define $q(x)=\frac12x^Tx$, then $\nabla_xq(x)=\frac x2$ and $\nabla_{xx}q(x)=\frac12\succ0$. So it's a convex QP.

define $L(x)=\frac12x^Tx-\lambda(a^Tx-b)$, then $\nabla L=\frac x2-\lambda a$. With $\nabla L=0$, we get $x^*=2\lambda a$. With $a^Tx^*=b$, then $2\lambda a^Ta=b$ which infer $\lambda=\frac{b}{2a^Ta}$.

So $x^*=\frac{ba}{a^Ta}$

## Q3

Solve the equality-constrained quadratic problem:
$$
\min \frac32x_1^2-x_1x_2+x_2^2-x_2x_3+\frac12x_3^2+x_1+x_2+x_3\\
s.t. x_1+2x_2+x_3=4
$$

## answer

Define $x = (x_1,x_2,x_3)^T$ and $q(x)=\frac12x^TGx+x^Tc$ with $G=\left(\begin{array}{ccc}3& -1&0\\-1&2&-1\\0&-1&1\end{array}\right)$ and $c=(1,1,1)^T$. From equality constrain, we get $A=(1,2,1)$ and $b=4$.

So we get the Null space of A which is $Z=\left(\begin{array}{cc}2&1\\-1&0\\0&1\end{array}\right)$. Then $Z^TGZ\succ 0$, is nonsingular, hence there is an unique global solution.

With KKT condition and schur-complement method, we get:
$$
C=G^{-1}-G^{-1}A^T(AG^{-1}A^T)^{-1}AG^{-1}\\
=\left(\begin{array}{ccc}5/18&-1/18&-1/6\\-1/18&1/9&-1/6\\-1/6 &-1/6&1/2\end{array}\right)
$$

$$
E=G^{-1}A^T(AG^{-1}A^T)^{-1}=\left(1/9,5/18,1/3\right)^T
$$

$$
F = -(AG^{-1}A^T)^{-1}=-1/18
$$

At last
$$
x^*=-Cd+Eb=(7/18,11/9,7/6)^T,\lambda^*=E^Td-Fb=17/18
$$

## Q4

Solve the inequality-constrained problem:
$$
\min 3x_1^2+3x_2^2-10x_1-24x_2\\
s.t. -2x_1-x_2\geq-4\\
x_1,x_2\geq0
$$
with the starting feasible point $x^{(0)}=(0,0)^T$

##answer

Define $q(x)=\frac12x^TGx+x^Tb$ with $G=\left(\begin{array}{cc}6&0\\0&6\end{array}\right)$ and $d=(-10,-24)^T$.

Label the constrains as 1,2,3 respectively. With the starting point, we get starting working set $W_0=\{2,3\}$. 

So we get suboptimal problem as:
$$
\min \frac12p^TGp+g_0^Tp\\
s.t. \space \space\space \space a_i^Tp=0\space \space  \space \space i=2,3
$$
With $g_0=Gx_0+d=(-10,-24)^T$, the suboptimal problem can be solved and we get $p = (0,0)^T$.

Then we compute $\lambda_2,\lambda_3$ from $\lambda_ 2a_2^T+\lambda_3 a_3^T=g_0$ and get $\lambda_2=-10,\lambda_3=-24$.

So we remove constrain 3 from the working set, because it has the most negative multiplier, and set $W_1=\{2\}$.

With $x_1=x_0+p$, we get $x_1=(0,0)^T$

 Iteration 2 starts by solving the suboptimal problem with working set $W_1=\{2\}$. Then we get $p=(0,4)^T$. The step-length formula yields $\alpha_2=1$ with the blocking constrain 1. So $W_2=\{1,2\}$ and $x_2=x_1+\alpha_2p=(0,4)^T$.

Iteration 3 starts by solving the suboptimal problem with working set $W_2=\{1,2\}$. Then we get $p=(0,0)^T$. We deduce that the Lagrange multiplier for the working constraint is $\lambda_1=0,\lambda_2=-10$, so we drop 2 from working set to obtain $W_3=\{1\}$. And $x_3=(0,4)^T$ 

 Iteration 4 starts by solving the suboptimal problem with working set $W_3=\{1\}$. Then we get $p=(1/3,-2/3)^T$. The step-length formula yields $\alpha_4=1$. So $W_4=\{1\}$ and $x_4=x_3+p=(1/3,10/3)^T$.

Iteration 5 starts by solving the suboptimal problem with working set $W_4=\{1\}​$. Then we get $p=(0,0)^T​$. We deduce that the Lagrange multiplier for the working constraint is $\lambda_1=0​$, so we get the final solution which is $x^*=(1/3,10/3)^T​$