# 2.1 Fields
## 2.1 Definition (field)
A field is a set $F$ together with binary operations on $F$, which we will refer to as addition and multiplication where:
- addition on $F$ forms an abelian group
- multiplication on $F^\times \equiv F / \{0 \}$ is an abelian group
- distribuivity: $\forall a,b,c \in F, \ a(b+c)=ab+ac$

## 2.2 Example
### 2.2.a
The sets $\mathbb{Q,R,C}$ are fields with add and multiply.

### 2.2.b
The set $\mathbb{F}_p=\{\bar{0}, \bar{1}, \dots , \overline{p-1} \}$ where $p$ is prime is a field under addition and remainder multiplication

## 2.3 Proposition
$F$ is a field
1. $\forall a \in F, \ 0a=0$
2. $\forall a,b \in F, \ (-a)b=-(ab)$

### proof
$$
\begin{align}
0+0a & = a0 \\
(0+0)a & = a0 \Rightarrow \\
0+0a & = 0a+0a \Rightarrow a0=0 \\
\end{align}
$$
For the second show that $(-a)b$ is the additive inverse for $a$

# 2.2 Vector spaces
## 2.4 Definition (vector space)
A **vector space** over $F$ is an albenian group $V$ under the map $F \times V \rightarrow V: (a,x) \mapsto ax$ (scalar multiplication)

### Vector space axioms
1. $\forall a,b \in F, \forall x \in V, \ (a+b)x=ax+bx \in V$ (1st distributivity law)
2. $\forall a \in F, \forall x,y \in V,\ a(x+y)=ax+ay \in V$ (2nd distribuitiy law)
3. $\forall a,b \in F, \forall x \in V, \ (ab)x=a(bx) \in V$
4. $\forall x \in V, 1x=x \in V$

vectors: elements of $V$ ($0_F$)
scalars: elements of $F$ ($0_V$)

## 2.5 Example
### 2.5.a
For any field $F$ the set $F^{n} \equiv \{(a_1, \dots , a_n) : a_1, \dots, a_n \in F \}$ is a vector space under component addition and scalar multiplication over $F$.  For example, $\mathbb{F}_2 ^2= \{ (0,0),(0,1),(1,0),(1,1) \}$ is a vector space over $\mathbb{F}_2$
### 2.5.b
![[Pasted image 20210209180317.png]]

## 2.6 Proposition
1. $(a-b)x=ax-bx$
2. $a(x-y)=ax-ay$
3. $ax=0v \Leftrightarrow a= 0_F \text { or } x=0_V$
4. $(-1)x=-x$

## 2.7 Example
$$ F^S \equiv \{ f:S \rightarrow F \} \text{ where S is a set and F is a field}$$
denotes the set of all maps from $S$ to $F$ where
$$
\begin{align}
& \forall s \in S, \ (f+g)(s) \equiv  f(s)+g(s) \text{ (addition)} \\
& \forall s \in S, \ (af)(s) \equiv a f(s) \text{ (scalar multiplication)}\\
\end{align}
$$
$F^S$ is a vector space over $F$.

# 2.3 Subspaces

## 2.8 Definition (subspace)
V is a vector space over field $F$. $W$ of $V$ is a subspace of $V$ if:
1. $0_V \in W$ (addition identity)
2. $\forall x,y \in W, x+y \in W$ (closed under addition)
3. $\forall a \in F, \forall x \in W, \ ax \in W$ (closed under scalar multiplication)

## 2.9 Proposition
$V$ a vector space over a field $F$ and $W$ subspace of $V \Rightarrow$ $W$ is a vector space over $F$

## 2.10 Example
Note: $\mathbb{R}^\mathbb{N}$ is the set of all functions $\mathbb{N} \rightarrow \mathbb{R}$

- subspace $\mathbb{R}^n$: nullspace of $M_n(\mathbb{R})$ or $col(M_n(\mathbb{R}))$
- subspace $\mathbb{R}^\mathbb{N}$ : the set of convergent sequences of $\mathbb{R}^n$ e.g. $(a_1, a_2, \dots)$
- 