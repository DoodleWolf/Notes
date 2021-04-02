# Linear Algebra II (MATH1049)
# Coursework 4

## Exercise 1
Which conditions for being a subspace are satisfied for the following subsets of 
$M_{n \times n} ( \mathbb{R})$? ($n \geq 2$)
$$
\begin{align}
U & \equiv \{ A \in M_{n \times n}(\mathbb{R}) : rank(A) \leq 1 \} \\
V & \equiv \{ A \in M_{n \times n}(\mathbb{R}) : \operatorname{det}(A)=0 \}\\
W & \equiv \{ A \in M_{n \times n}(\mathbb{R}) : \operatorname{trace}(A)=0 \}\\
\end{align}
$$

### Solution
a) $U  \equiv \{ A \in M_{n \times n}(\mathbb{R}) : rank(A) \leq 1 \}$
1. Additive identity $\checkmark$


$$
\begin{align}
0_V &=
\begin{pmatrix}
0 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & 0
\end{pmatrix} _{n \times n}\\
\operatorname{rank}(0_V) &= 0 \Rightarrow 0_V \in U\\
\end{align}
$$
2. Additive closure $\times$
Take $n=2$ so $M_{2 \times 2}$

$$
\begin{align}
\operatorname{rank}(
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
)=1 \Rightarrow
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
\in U \\
\operatorname{rank}(
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
)=1 \Rightarrow
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
\in U \\
\operatorname{rank}(
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} +
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix})=2 \Rightarrow 
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} +
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix} \notin U
\end{align}
$$
3. Scalar closure $\checkmark$

$$
\begin{align}

 \forall  \lambda \in \mathbb{R}\backslash \{0 \} , \forall A \in U \subset M_{m \times n}(\mathbb{R}),\ \operatorname{rank}(\lambda A)=\operatorname{rank}(A) \tag{Thm. 3.33 (ii) LA 1} \\
 A \in U\Rightarrow \operatorname{rank}(\lambda A)=\operatorname{rank}(A) \leq 1 \\
 \Rightarrow \operatorname{rank}(\lambda A) \leq 1 \Rightarrow \lambda A \in U \\
 \Rightarrow \forall  \lambda \in \mathbb{R}\backslash \{0 \} , \forall A \in U,\ \lambda A \in U
\end{align}
$$
$$
\begin{align}
\text{Let } \lambda=0 \\
\forall A \in U, \lambda A = 0_V \tag{Additive identity scalar} \\
0_V \in U \Rightarrow \forall A \in U, \lambda A \in U \text{ where } \lambda=0
\end{align}
$$
Since cases $\lambda = 0$ and $\lambda \in \mathbb{R}\backslash \{0 \}$ have been proved to be closed we can conclude that $U$ is closed under scalar multiplication

b) $V \equiv \{ A \in M_{n \times n}(\mathbb{R}) : \operatorname{det}(A)=0 \}$
1. Additive Identity $\checkmark$

$$
\begin{align}
0_V &=
\begin{pmatrix}
0 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & 0
\end{pmatrix} _{n \times n}\\
\text{(two identical rows)} \Rightarrow \operatorname{det}(0_V) &= 0 \Rightarrow 0_V \in V\\
\end{align}
$$

2. Additive Closure $\times$

Take $n=2$ so $M_{2 \times 2}$
$$
\begin{align}
\operatorname{det}(
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
)=1*0+0*0=0 \Rightarrow
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
\in V \\
\operatorname{det}(
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
)=0*1+0*0=0 \Rightarrow
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
\in V \\
\operatorname{det}(
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} +
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix})=1*1+0*0=1 \Rightarrow 
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} +
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix} \notin V
\end{align}
$$

3. Scalar Closure $\checkmark$

$$
\begin{align}
\forall  \lambda \in \mathbb{R} , \forall  A \in V \subset M_{n \times n}, \ \operatorname{det}(\lambda A)=\lambda^n\operatorname{det}(A) \tag{ Def. 4.1 D1 (i) LA 1} \\
A \in V \Rightarrow \operatorname{det}(\lambda A)=\lambda^n \cdot 0=0 \\
\Rightarrow \operatorname{det}(\lambda A) \in V \\
\Rightarrow  \forall  \lambda \in \mathbb{R} , \forall  A \in V \subset M_{n \times n}, \ \operatorname{det}(\lambda A) \in V
\end{align}
$$

c) $W  \equiv \{ A \in M_{n \times n}(\mathbb{R}) : \operatorname{trace}(A)=0 \}$

1. Additive Identity $\checkmark$

$$
\begin{align}
0_V &=
\begin{pmatrix}
0 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & 0
\end{pmatrix} _{n \times n}\\
\ \operatorname{trace}(0_V) &= 0^n=0 \Rightarrow 0_V \in W\\
\end{align}
$$

2. Additive closure $\times$

Take $n=2$ so $M_{2 \times 2}$
$$
\begin{align}
\operatorname{trace}(
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
)=1*0=0 \Rightarrow
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
\in W \\
\operatorname{trace}(
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
)=0*1=0 \Rightarrow
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
\in W \\
\operatorname{trace}(
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} +
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix})=1*1=1 \Rightarrow 
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} +
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix} \notin W
\end{align}
$$

3. Scalar Closure $\checkmark$

$$
\begin{align}
\text{Let } A \in W, \ A=(a_{ij}) \\
\Rightarrow \operatorname{trace}(A)=0\\
\Rightarrow a_{11}\times a_{22} \times \dots \times a_{nn} = 0 \\
\Rightarrow \lambda^n \times na_{11}\times \dots \times  a_{nn}=0 \text{ where } \lambda \in \mathbb{R}\\
\Rightarrow \operatorname{trace}(\lambda A)=0
\Rightarrow \lambda A \in W\\
\Rightarrow \forall \lambda \in \mathbb{R}, \forall A \in W, \ \lambda A \in W
\end{align}
$$

## Exercise 2
Which of these are are subspaces of $\mathbb{R}^\mathbb{R}$?
$$
\begin{align}
U & \equiv \{ f \in \mathbb{R}^\mathbb{R} : \text{$f$ is diff. and  } f'(-5)=0 \} \\
V & \equiv \{ f \in \mathbb{R}^\mathbb{R} : \exists a \in [0 ,\infty) : \forall s \in \mathbb{R} : f(s)=as^2 \} \\
W & \equiv \{ f \in \mathbb{R}^\mathbb{R} : \exists i \in \{3,5 \}, \exists a \in \mathbb{R} : \forall s \in \mathbb{R} : f(s)=as^i \} \\
X & \equiv \{ f \in \mathbb{R}^\mathbb{R} : \text{$f$ is even} \} \\
\end{align}
$$

### Solution
a) $U  \equiv \{ f \in \mathbb{R}^\mathbb{R} : f \text{ is diff. and  } f'(-5)=0 \}$

1. Additive Identity $\checkmark$

 $$
\begin{align}
\forall x \in \mathbb{R}, \underline{0}(x)=0 \\
\underline{0}'(x)=0 \Rightarrow \underline 0(x) \in U 
\end{align}
$$
2. Additive closure $\checkmark$

$$
\begin{align}
\text{Let }f, g \in U \\
(f+g)(x)=f(x)+g(x)\\ 
\Rightarrow (f+g)(x) \text{ is diff.} \tag{Calculus} \\
(f+g)'(x)=f'(x)+g'(x) \\
(f+g)'(-5)=f'(-5)+g'(-5)=0 \tag{Definition of $U$} \\ 
(f+g)(x) \text{ is diff. and } (f+g)'(-5)=0 \\
\Rightarrow (f+g)(x) \in U
\end{align}
$$

3. Scalar closure $\checkmark$

$$
\begin{align}
\text{Let } f \in U, \lambda \in \mathbb{R}\\
(\lambda f)(x)=\lambda(f(x)) \\
\Rightarrow (\lambda f)(x) \text{ is diff.} \tag{Calculus}\\
(\lambda f)'(x)=\lambda f'(x) \\
(\lambda f)'(-5)=\lambda f'(-5)=0 \tag{Definition of $U$}
\end{align}
$$
Since 1.-3. hold $U$ is a subspace.

b) $V  \equiv \{ f \in \mathbb{R}^\mathbb{R} : \exists a \in [0 ,\infty) : \forall s \in \mathbb{R} : f(s)=as^2 \}$

1. Additive identity $\checkmark$

$$
\underline{0}(x)=0=0*x^2 \Rightarrow \underline{0}(x) \in V
$$

2. Additive closure $\checkmark$
$$
\begin{align}
\text{Let } f,g \in V\\
\Rightarrow f(x)=ax^2, \ g(x)=bx^2 \text{ where }a,b \in [0, \infty) \\
(f+g)(x)=f(x)+g(x)=ax^2+bx^2=(a+b)x^2 \\
a, b \in [0, \infty) \Rightarrow a \geq0, \ b \geq0 \Rightarrow a+b \geq 0 \Rightarrow a+b \in [0,\infty)\\
\Rightarrow (f+g)(x) \in V
\end{align}
$$

3. Scalar closure $\times$

$$
\begin{align}
\text{Let } f=x^2 , \lambda=-1 \\
1 \in [0, \infty) \Rightarrow f=1\cdot x^2 \in V \\
(-1 \cdot f)(x)=-x^2 \\
-1 \notin [0, \infty) \Rightarrow (-1 \cdot f)(x) \notin V
\end{align}
$$
Since scalar multiplication closure does not hold in $V$, $V$ is not a subspace of $\mathbb{R}^\mathbb{R}$.

c) $W \equiv \{ f \in \mathbb{R}^\mathbb{R} : \exists i \in \{3,5 \}, \exists a \in \mathbb{R} : \forall s \in \mathbb{R} : f(s)=as^i \}$

Counter-example to additive closure
$$
\begin{align}
\text{Let } f(x)=x^3, g(x)=x^5\\
1 \in \mathbb{R} \Rightarrow f,g \in W \\
(f+g)(x)=f(x)+g(x)=x^3+x^5 \\
\text{(not in the form $ax^3$ or $ax^5$)}\\
\Rightarrow (f+g)(x) \notin W
\end{align}
$$
Since addition is not closed in $W$, $W$ is not a subspace of $\mathbb{R}^\mathbb{R}$.

d) $X \equiv \{ f \in \mathbb{R}^\mathbb{R} : f \text{ is even} \}$

1. Additive Identity $\checkmark$

$$
\underline 0(x)=0 = \underline 0 (-x) \Rightarrow \underline{0}(x) \text{ is even}
$$

2. Additive closure $\checkmark$

$$
\begin{align}
\text{Let } f,g \text{ be even functions}\\
\Rightarrow f,g \in X \\
(f+g)(x)=f(x)+g(x) \\
(f+g)(-x)=f(-x)+g(-x)=f(x)+g(x)=(f+g)(x) \tag{$f$,$g$ are even}\\
\Rightarrow (f+g)(-x)=(f+g)(x)\\
\Rightarrow (f+g)(x) \text{ is an even function}\\
\Rightarrow (f+g)(x) \in X
\end{align}
$$

3. Scalar closure $\checkmark$

$$
\begin{align}
\text{Let $f$ be an even function}, \lambda \in \mathbb{R}\\
\Rightarrow f \in X \\
( \lambda f)(x) = \lambda (f(x)) \\
(\lambda f)(-x)= \lambda (f(-x))= \lambda (f(x)) = (\lambda f)(x) \tag{$f$ is even} \\
\Rightarrow (\lambda f)(x)=(\lambda f)(-x) \\
\Rightarrow \lambda f \text{ is even} \\
\Rightarrow \lambda f \in X
\end{align}
$$
Since 1.-3. hold, $X$ is a subspace of $\mathbb{R}^\mathbb{R}$

## Exercise 3

**a)**  Let $V$ be a vector space over $\mathbb{F}_2$. Show that every non-empty subset $W$ of $V$ which is closed under addition is a subspace of $V$ .
**b)** Show that $\{ (0, 0),(1, 0)\}$ is a subspace of the vector space $\mathbb{F}_2^2$ over $F_2$.
**c)** Write down all subsets of $\mathbb{F}_2^2$ and underline those subsets which are subspaces.

### Solutions

a) Let $V$ be a vector space over $\mathbb{F}_2$. Show that every non-empty subset $W$ of $V$ which is closed under addition is a subspace of $V$.
1. Additive identity

$$
\begin{align}
\text{Let } a \in W, \\
a+a \in W \tag{additive closure} \\
\Rightarrow (1+1)a \in W \tag{Distributivity in V} \\
0a=0_V \in W \tag{Addition in $\mathbb{F}_2$ + identity multip.}
\end{align}
$$
3. Scalar multiplication

$$
\begin{align}
\text{Let } a \in W, \\
0a = 0_V \tag{Identity multiplication}\\
1a=a \in W \tag{Definition of 1 multip.}
\end{align}
$$

Since all three conditions hold $W$ is a subspace of $V$

b) Showing $\{ (0, 0),(1, 0)\}$ is a subspace of $\mathbb{F}_2^2$ over $F_2$

1. Additive identity

$$
(0,0) \in \{ (0, 0),(1, 0)\}
$$

2. Additive closure
$$
\begin{align}
(0,0)+(0,1)=(0,1) \in \{ (0, 0),(1, 0)\} \\
(0,1)+(0,1)=(0,0) \in \{ (0, 0),(1, 0)\} \\ 
(0,0)+(0,0)=(0,0) \in \{ (0, 0),(1, 0)\} \\
(0,1)+(0,0)=(0,1) \in \{ (0, 0),(1, 0)\} 
\end{align}
$$

3. Scalar multiplication

$$
\begin{align}
1*(0,0)=(0,0) \in \{ (0, 0),(1, 0)\} \\
0*(0,0)=(0,0) \in \{ (0, 0),(1, 0)\} \\
1*(0,1)=(0,1) \in \{ (0, 0),(1, 0)\} \\
0*(0,0)=(0,0) \in \{ (0, 0),(1, 0)\} 
\end{align}
$$

c) Write down all subsets of $\mathbb{F}_2^2$ and underline those subsets which are subspaces.
$$
\begin{align}
 \mathcal{P}(\mathbb{F}_2^2)= | \emptyset , \fbox{\{(0,0)\}}, \{ (0,1) \}, \{ (1,0) \}, \{ (1,1) \},\\
\fbox{\{(0,0),(0,1) \}}, \fbox{\{(0,0),(1,0)\}}, \fbox{\{(0,0),(1,1)\}} , \{ (0,1),(1,0) \} , \{ (0,1), (1,1) \}, \{ (1,0), (1,1) \}, \\
\{ (0,0),(1,0)(0,1) \}, \{ (0,0),(1,0),(1,1) \}, \{ (0,0),(0,1),(1,1) \}, \{ (0,1),(1,0),(1,1) \}, \\ \fbox{\{(0,0),(0,1),(1,0),(1,1)\}}
|
\end{align}
$$