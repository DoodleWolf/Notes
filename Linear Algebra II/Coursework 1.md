# Linear Algebra II (MATH1049)

## Exercise 1
$G$ and $H$ are groups with binary operations $\boxplus$ and $\odot$
Show that $*$ defined by
$$\forall a, a' \in G, \forall b,b' \in H, \ (a,b) * (a', b') \equiv (a \boxplus a', b \odot b')$$
forms a group in $G \times H$.

### Solution
To show that $G \times H$ is a group under $*$ the following properties must be checked: closure, associativity, identity existence, inverse existence.

1. Closure
$$
\begin{align}
\forall (a,b), (a',b') \in G \times H, \ &(a,b)*(a',b') \in G \times H \\
&(a \boxplus a', b \odot b') \in G \times H
\end{align}
$$
Therefore to show closure $a \boxplus a' \in G$ and $b \odot 'b \in H$ must be shown but these are given since $G$ and $H$ are groups under $\boxplus$ and $\odot$.

1. Associativity
$$ 
\begin{align}
\forall a_1 , a_2, a_3, \in G, \forall b_1, b_2, b_3, \in H, \
((a_1, b_1) * (a_2, b_2)) * (a_3, b_3) & = (a_1, b_1) * ((a_2, b_2) * (a_3, b_3))\\
(a_1 \boxplus a_2, b_1 \odot b_2) * (a_3, b_3) & = (a_1, b_1) * (a_2 \boxplus a_3, b_2 \odot b_3)\\
( (a_1 \boxplus a_2) \boxplus a_3 , (b_1 \odot b_2) \odot b_3) & = (a_1 \boxplus (a_2 \boxplus a_3), b_1 \odot (b_2 \odot b_3))\\
\end{align}
$$
Therefore to show associativity it must be shown that $\forall a_1, a_2, a_3 \in G, \ a_1 \boxplus (a_2 \boxplus a_3)$ and  $\forall b_1, b_2, b_3, \in H, (b_1 \odot b_2) \odot b_3=b_1 \odot (b_2 \odot b_3)$
$$
\begin{align}
 G \text{ is a group under } \boxplus \Rightarrow \forall a_1,a_2, a_3 \in G, \  (a_1 \boxplus a_2) \boxplus a_3 &= a_1 \boxplus (a_2 \boxplus a_3) \\
 H \text{ is a group under } \odot \Rightarrow \forall b_1, b_2, b_3 \in H, \  (b_1 \odot b_2) \odot b_3 &= b_1 \odot (b_2 \odot b_3) \\
 \end{align}
 $$
 Hence associativity holds
 
2. Identity existence
$$
\begin{align}
\exists (e_G, e_H) \in G \times H, \forall (a,b) \in G  \times H, \ (e_G, e_H) * (a,b) = &(a,b) = (a,b) * (e_G, e_H) \\
(e_G \boxplus a, e_H \odot b) = &(a,b) = (a \boxplus e_G, b \odot e_H)
\end{align}
$$
Therefore to show the existence of an identity it must be shown that $\exists e_G \in G, \forall a \in G, \ e_G \boxplus a = a = a \boxplus e_G$ and $\exists e_H \in H, \forall b \in H, \ e_H \odot b = b = b \odot e_H$
$$
\begin{align}
 G \text{ is a group under } \boxplus \Rightarrow \exists e_G \in G, \forall a \in G, \ e_G \boxplus a = a = a \boxplus e_G \\
 H \text{ is a group under } \odot \Rightarrow \forall \exists e_H \in H, \forall b \in H, \ e_H \odot b = b = b \odot e_H \\
 \end{align}
 $$
 Hence the existence of an identity holds. 
 (from this it can also be seen that the identity in the group $G \times H$ under $*$ is the combination of the identities from $G$ and $H$ under $\boxplus$ and $\odot$)
 
 3. Inverse existence
 $$
 \begin{align}
 \forall (a,b) \in G \times H, \exists (a',b') \in G \times H, \ (a,b) * (a',b') &= (e_G, e_H) \text{ where } (e_G, e_H) \text{ is the identity} \\
 (a \boxplus a', b \odot b') &= (e_G, e_H)
 \end{align}
 $$
 Therefore to show the existence of an inverse for each element it must be shown $\forall a \in G, \exists a' \in G, \ a \boxplus a' = e_G \text{ where } e_G \text{ is the identity in } G \text{ under } \boxplus$ and the similar statement for $H$ under $\odot$.
$$
\begin{align}
 G \text{ is a group under } \boxplus \Rightarrow \forall a \in G, \exists a' \in G, \ a \boxplus a' = e_G \text{ where } e_G \text{ is the identity in } G \text{ under } \boxplus \\
 H \text{ is a group under } \odot \Rightarrow \forall b \in H, \exists b' \in H, \ b \boxplus b' = e_H \text{ where } e_H \text{ is the identity in } H \text{ under } \odot \\
 \end{align}
 $$
 Hence there exists an inverse for each element in $G \times H$ under $*$
 
 Since associativity, identity existence and inverse existence have been shown to hold in $G \times H$ under $*$ it follows that $G \times H$ is a group with the binary operation $*$.
 
 ## Exercise 2
 
$G$ is defined as $G \equiv \mathbb{R}\backslash \{-1\}$ and the operation $*$ is defined as 
 $$\forall a,b \in \mathbb{R}, \ a * b \equiv a+b+ab \in \mathbb{R}$$
 
 a) Show that $\forall a,b \in G, \ a * b \in G$
 b) Show that $G$ forms a group under $* : G \times G \rightarrow G, (a,b) \mapsto a * b$
 
 ### Solution
 
##### 2.a

^aa218c

 Take the contrapositive of $\forall a,b \in G, \ a * b \in G$
 $$ 
 \exists a,b \in G, \ a*b \notin G \\
 $$
 Since multiplication and addition is closed in $\mathbb{R}$ the following statement is equivalent
 $$
 \begin{align}
 \exists a,b \in G, \ a*b &= -1\\
 a+b+ab &= -1\\
 a(1+b) &=-(1+b)\\
 \text{either } a=-1 &\text{ or }b=-1
 \end{align}
 $$
 This cannot be since $a,b \in \mathbb{R}\backslash \{-1\}$ therefore the contrapositive is false and our intial statement holds.
 
##### 2.b
To show that $G$ is a group under $*$ the following properties must be shown to hold: closure, associativiy, identity existence, inverse existence.
1. Closure
Holds from [[#^aa218c | 2.a]]

2. Associativity
$$
\begin{align}
\forall a,b,c \in G, \ (a*b)*c &=a*(b*c) \\
(a+b+ab)*c &=a*(b+c+bc)\\
a+b+ab + c + (a+b+ab)c &= a + b + c + bc + a(b + c + bc) \\
0 &= 0
\end{align}
$$
Therefore associativity holds.

3. Identity existence
$$
\begin{align}
\exists e \in G,\forall a \in G, \ ea= &a=ae\\
e+a+ae= &a=e+a+ea\\
\text{ (LHS} = \text{RHS}) \Rightarrow e+a+ae&=a \\
e(1+a)=0 \\
\Rightarrow e=0 \text{ since } a \neq -1
\end{align}
$$
The identity exists and is in $G$

4. Inverse existence
$$
\begin{align}
\forall a \in G, \exists a' \in G, \ a*a'&=e \text{ where } e \text{ is the identity in } G \text{ under } * \\
a+a'+aa'&=0\\
a'(1+a)&=-a\\
a'= -\frac {a}{1+a}
\end{align}
$$
since $a \neq -1$ the inverse will always exist. Now to check that $a' \in G$. Assume the opposite,
$$
\begin{align}
a' &\notin G \\
-\frac{a}{1+a} &\notin G \text{ where } a \in G\\
\text{(division is closed in } \mathbb{R}) \Rightarrow -\frac{a}{1+a} &=-1 \\
a \in G \Rightarrow a \neq -1 \Rightarrow a&=1+a \\
0 &= 1 \Rightarrow a' \in G
\end{align}
$$
Therefore the inverse exists and is in $G$.

## Exercise 3
$G= \{ s,t,u,v \}$ be a group under $*$ with $s*u=u$ and $t*t=v$. Determine the group table for $G$ step-by-step.

### Solution
1. Initial 

$$
\begin{array}{|c|c|c|c|c|} \hline
* & s & t & u & v \\ \hline
s &  &  &  &  \\ \hline
t &  & v &  &  \\ \hline
u & u &  &  &  \\ \hline
v &  &  &  &  \\ \hline
\end{array}
$$

2. Input identity
From Proposition 1.3 a group can only have one identity and $s*u=u$, hence $s$ is the identity

$$
\begin{array}{|c|c|c|c|c|} \hline
* & s & t & u & v \\ \hline
s & s & t & u & v \\ \hline
t & t & v &  &  \\ \hline
u & u &  &  &  \\ \hline
v & v &  &  &  \\ \hline
\end{array}
$$

3. $u*u=v$
$s$ is the identity => $\forall a \in G \backslash \{s\}, \ v*a \neq v$
$t*t=v$ => $t*u \neq v$ and $u*t \neq v$ (Prop. 1.4 says there must be a unique solution)
(Prop. 1.4 there must be a unique solution to $u*\ ?=v$) => $u*u=v$

$$
\begin{array}{|c|c|c|c|c|} \hline
* & s & t & u & v \\ \hline
s & s & t & u & v \\ \hline
t & t & v &  &  \\ \hline
u & u &  & v &  \\ \hline
v & v &  &  &  \\ \hline
\end{array}
$$

4. $t*v=v*t=u$
Prop 1.4 => $t* \ ? =u$ and $?*t=u$ must be unique
$s*u=u*s=u$ => $t*u \neq u$ and $u*t \neq u$
leaving only $t*v=v*t=u$ 

$$
\begin{array}{|c|c|c|c|c|} \hline
* & s & t & u & v \\ \hline
s & s & t & u & v \\ \hline
t & t & v &  & u \\ \hline
u & u &  & v &  \\ \hline
v & v & u &  &  \\ \hline
\end{array}
$$

5. $t*u=u*t=s$
$s$ is the only element not found in the $t$ row and column

$$
\begin{array}{|c|c|c|c|c|} \hline
* & s & t & u & v \\ \hline
s & s & t & u & v \\ \hline
t & t & v & s & u \\ \hline
u & u & s & v &  \\ \hline
v & v & u &  &  \\ \hline
\end{array}
$$

6. $u*v=v*u=t$
$t$ is the only element not found in the $u$ row and column

$$
\begin{array}{|c|c|c|c|c|} \hline
* & s & t & u & v \\ \hline
s & s & t & u & v \\ \hline
t & t & v & s & u \\ \hline
u & u & s & v & t \\ \hline
v & v & u & t &  \\ \hline
\end{array}
$$

7. $v*v=s$
$s$ is the only element not found in the $v$ row and column

$$
\begin{array}{|c|c|c|c|c|} \hline
* & s & t & u & v \\ \hline
s & s & t & u & v \\ \hline
t & t & v & s & u \\ \hline
u & u & s & v & t \\ \hline
v & v & u & t & s \\ \hline
\end{array}
$$

## Exercise 4

a) Find the group table for $C_4$.
b) Find the group table for $C_2 \times C_2$ following $*$ from exercise 1
c) $\forall a \in C_4$ find the $\operatorname {sup} \{ m \in \mathbb{Z}_+ : ma = e \}$  where $e$ is the identity in $C_4$
d) $\forall (a,b) \in C_2 \times C_2$ find the $\operatorname {sup} \{ m \in \mathbb{Z}_+ : m(a,b) = e \}$  where $e$ is the identity in $C_2 \times C_2$

### Solutions

#### 4.a  group table for $C_4$
$$
\begin{array}{|c|c|c|c|c|} \hline
\oplus & \bar{0} & \bar{1} & \bar{2} & \bar{3} \\ \hline
\bar{0} & \bar{0} & \bar{1} & \bar{2} & \bar{3} \\ \hline
\bar{1} & \bar{1} & \bar{2} & \bar{3} & \bar{0} \\ \hline
\bar{2} & \bar{2} & \bar{3} & \bar{0} &  \bar{1}\\ \hline
\bar{3} & \bar{3} & \bar{0} & \bar{1} & \bar{2} \\ \hline
\end{array}
$$

#### 4.b group table for $C_2 \times C_2$
$$
\begin{array}{|c|c|c|c|c|} \hline
* & (\bar{0}, \bar{0}) & (\bar{0}, \bar{1}) & (\bar{1}, \bar{0}) & (\bar{1}, \bar{1}) \\ \hline
(\bar{0}, \bar{0}) & (\bar{0}, \bar{0}) & (\bar{0}, \bar{1}) & (\bar{1}, \bar{0}) & (\bar{1}, \bar{1}) \\ \hline
(\bar{0}, \bar{1}) & (\bar{0}, \bar{1}) & (\bar{0}, \bar{0}) & (\bar{1}, \bar{1}) & (\bar{1}, \bar{0}) \\ \hline
(\bar{1}, \bar{0}) & (\bar{1}, \bar{0}) & (\bar{1}, \bar{1}) & (\bar{0}, \bar{0}) & (\bar{0}, \bar{1}) \\ \hline
(\bar{1}, \bar{1}) & (\bar{1}, \bar{1}) & (\bar{1}, \bar{0}) & (\bar{0}, \bar{1}) & (\bar{0}, \bar{0}) \\ \hline
\end{array}
$$

#### 4.c
1. For $\bar{0},\ m=0$
2. For $\bar{1}, \ m=4$
3. For $\bar{2}, \ m=2$
4. For $\bar{3}, \ m=4$

#### 4.d
1. For $(\bar{0}, \bar{0}), \ m=0$
2. For $(\bar{0}, \bar{1}), \ m=1$
3. For $(\bar{1}, \bar{0}), \ m=1$
4. For $(\bar{1}, \bar{1}), \ m=1$

## Extra question
$G$ is a group under $+: G \times G \rightarrow G, (a,b) \mapsto a+b$
a) Show that $\forall a \in G, \forall \mathbb{Z}, \ m(na)=(mn)a$
b) Write the two exponential laws in additive notation.

### Solutions

#### part a
Break down into cases:
1. $m,n > 0$
$$ 
\begin{align}
m(na)&=(mn)a\\
m \overbrace{(a + \dots + a)}^{n \text{ times}} &= \overbrace{a+ \dots + a}^{mn \text{ times}}\\
\overbrace{(a + \dots + a)}^{mn \text{ times}} &= \overbrace{a+ \dots + a}^{mn \text{ times}}
\end{align}
$$

2. $m > 0, n < 0$
$$ 
\begin{align}
m(na)&=(mn)a\\
na=\overbrace{-a-\dots-a}^{n \text{ times}} \Rightarrow m(-n(-a))&=(-mn)(-a)\\
-n>0 \Rightarrow (-mn)(-a)&=(-mn)(-a)
\end{align}
$$

3. $m < 0, n > 0$
$$
\begin{align}
m(na) &= (mn)a\\
m(-n(-a)) &= (mn)(-1(-a))\\
\text{from 2.} \Rightarrow (-mn)(-a) &= (-mn)(-a)
\end{align}
$$

4. $m,n < 0$
$$
\begin{align}
m(na)&=(mn)a \\
-m,-n>0 \Rightarrow -m(-n)(a)&=(mn)(a)\\
(mn)(a)&=(mn)(a)
\end{align}
$$

9. $m=0$
Let $e$ be the identity of $G$
$$
\begin{align}
0(na)&=(0n)a\\
\text{let }b = na \Rightarrow 0b&=0a \\
e&=e
\end{align}
$$
11. $n=0$
$$
\begin{align}
m(0a)&=(m0)a\\
me&=0a\\
e&=e
\end{align}
$$

#### part b
Exponential laws:
1. $\forall m,n \in \mathbb{Z}, \forall a \in G, \ (m+n)(a)=ma+na$
2. If $G$ is abelian, $\forall m \in \mathbb{Z}, \forall a,b \in G, \ m(a+b)=ma+mb$ 
