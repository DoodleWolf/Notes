# 2.42 Example
## Alternating series
 $\sum \limits_{n=0}^{\infty}(-1)^{n}a_{n}$  where $\forall n>0, a_{n} > a_{n+1}$ and $\lim a_{n}=0$
$$ \begin{align} \text{(1.1) \quad let }\forall n, s_{2n}-s_{2n-2}=-a_{2n-1}+a_{2n}<0 \\
\text{(1.2) \quad let } \forall n,  s_{2n+1} - s_{2n-1}=a_{2n}-a_{2n+1}>0 \\
\text{(1.1)}\Rightarrow s_{2n+2} -s_{2n}=-a_{2n+1}+a_{2n+2} \text{ \quad add to (1.2)} \\
(s_{2n}-s_{2n-1})-(s_{2n+2}-s_{2n+1})=a_{2n}-a_{2n+2} \\
\text{hence } s_{2n} - s_{2n-1}=a_{2n} \\
\end{align}$$
$$\forall m <n, s_{2m-1} \leq _{\text{ (1.2) }} s_{2n-1} \leq _{\text{ (from above) }} s_{2n}$$
hence $s_{n}$ and $s_{2n-1}$ are bounded $\Rightarrow$ convergent. Since $s_{2n}$ < $s_{2n-1}$ but $a_{2n} \rightarrow 0$ so $s_{2n}=s_{2n-1}$ hence the series is convergent.