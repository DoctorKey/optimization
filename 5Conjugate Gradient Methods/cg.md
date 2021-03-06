# 5.2

Suppose if $\exists \lambda_0,\lambda_1,\dots,\lambda_l \neq0$ s.t. $\lambda_0p_0+\lambda_1p_1+\dots+\lambda_lp_l=0$ 

Since $p_0,p_1,\dots,p_l$ are nonzero vectors, without loss of generality, choose $i$ s.t. $p_i \neq 0$. 

Multiply $p_i^TA$, then get $\lambda_0p_{i}^{T}Ap_0 + \lambda_1p_1^TAp_1 + \dots + \lambda_lp_l^TAp_l = 0$.

Since $p_i^TAp_j = 0$ for all $i \neq j$, then we get $\lambda_ip_i^TAp_i = 0$.

Since $A\succ 0 $ and $p_i \neq 0$, so $\lambda_i = 0$. Then we get a conflict with suppose.

So there are no $\lambda_0,\lambda_1,\dots,\lambda_l $ which satisfy $\lambda_0,\lambda_1,\dots,\lambda_l \neq0$. So $p_0,p_1,\dots,p_l$ are independent.

# 5.3

With $x_{k+1} = x_k + \alpha_kp_k$ and $\Phi(x)=\frac{1}{2}x^TAx - b^Tx$, then we get

$$\Phi(x_{k+1}) = \frac12\alpha_k^2p_k^TAp_k + \alpha_k(x_k^TAp_k-b^Tp_k)+\frac12x_k^TAx_k-b^Tx_k$$

So $$\frac{\partial\Phi(x_{k+1})}{\partial\alpha_k}=\alpha_kp_k^TAp_k+x_k^TAp_k-b^Tp_k$$, force it to equal 0, then we get

$$\alpha_k = \frac{x_k^TAp_k-b^Tp_k}{p_k^TAp_k}=-\frac{(b^T-x_k^TA)p_k}{p_k^TAp_k}=-\frac{r_k^Tp_k}{p_k^TAp_k}$$

# 5.4

For $f(x)$ is a strictly convex quadratic, $\lambda_1f(x_1)+\lambda_2f(x_2)\geq f(\lambda_1x_1+\lambda_2x_2)$.

$$
\lambda_1h(\sigma^1)+\lambda_2h(\sigma^2)\\
=\lambda_1f(x_0+\sigma_0^1p_0+\dots+\sigma_{k-1}^1p_{k-1})+\lambda_2f(x_0+\sigma_0^2p_0+\dots+\sigma_{k-1}^2p_{k-1})\\
\geq f((\lambda_1+\lambda_2)x_0+(\lambda_1\sigma_0^1+\lambda_2\sigma_0^2)p_0+\dots+(\lambda_1\sigma_{k-1}^1+\lambda_2\sigma_{k-1}^2)p_{k-1}))\\
=h(\lambda_1\sigma^1+\lambda_2\sigma^2)
$$

# 5.5

$$
r_1 = Ax_1-b=A(x_0+\alpha_0p_0)-b=r_0+\alpha_0Ap_0=r_0-\alpha_0Ar_0
$$

$$
p_1=-r_1+\beta_1p_0=-r_1-\beta_1r_0
$$

# 5.6

from (5.14d), we get
$$
\beta_{k+1} = \frac{r_{k+1}^TAp_k}{p_k^TAp_k}
$$
from (5.10), we get
$$
\alpha_kAp_k=r_{k+1}-r_{k}
$$
multiply this formula with $r_{k+1}^T$, then we get
$$
\alpha_kr_{k+1}^TAp_k=r_{k+1}^Tr_{k+1}-r_{k+1}^Tr_k
$$
Since $\alpha_k=\frac{r_k^Tr_k}{p_k^TAp_k}$ and (5.16), then
$$
r_k^Tr_k*\frac{r_{k+1}^TAp_k}{p_k^TAp_k}=r_{k+1}^Tr_{k+1}\\
\beta_{k+1}=\frac{r_{k+1}^Tr_{k+1}}{r_k^Tr_k}
$$

# 5.7

$$
[I+P_k(A)A]^TA[I+P_k(A)A]v_i=[I+P_k(A)A]^TA[v_i+P_k(A)Av_i]\\
=[I+P_k(A)A]^TA[v_i+\lambda_iP_k(A)v_i]=[I+P_k(A)A]^TA[v_i+\lambda_iP_k(\lambda_i)v_i]\\
=[I+P_k(A)A]^T\lambda_iv_i[I+\lambda_iP_k(\lambda_i)]=\lambda_i[I+\lambda_iP_k(\lambda_i)]^2v_i
$$











