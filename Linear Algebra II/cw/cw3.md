# Linear Algebra II (MATH1049) — Coursework Sheet 3 — 2020/21

## Exercise 1

Define $a \otimes \mathbf{x} \equiv { ax_1 \choose 0}$
$$\otimes : \mathbb{R} \times \mathbb{R}^2 \rightarrow \mathbb{R}^2: (a, \mathbf{x}) \mapsto a \otimes \mathbf{x} \text{ where } a \in \mathbb{R}$$
and determine which of the properties of a vector space hold when $\otimes$ is used as scalar multiplication in $\mathbb{R}^2$

#### solution

1. (**1st distribuitivity law**) $\forall a,b \in \mathbb{R}, \forall x \in \mathbb{R}^2, \ (a+b)\otimes x=a \otimes x+b \otimes x \in \mathbb{R}^2$
$$
\begin{align}
(a+b) \otimes x &= a \otimes x + b \otimes x \\
x \in \mathbb{R}^2 \Rightarrow x \equiv {x_1 \choose x_2} \text{ where } x_1 , x_2 \in \mathbb{R} &\Rightarrow \\
{(a+b)x_1 \choose 0} &= { ax_1 \choose 0} + {bx_1 \choose 0} \tag{Definition of $\otimes$}\\
{(a+b)x_1 \choose 0} &= { ax_1 + bx_1 \choose 0} \tag{Addition of $\mathbb{R}^2$} \\
{(a+b)x_1 \choose 0} &= { (a+b)x_1 \choose 0}  \tag{Distributivity of $\mathbb{R}$}\\
&\ \checkmark
\end{align}
$$
Since $\mathbb{R}$ is closed under addition and multiplication $(a+b)x_1 , 0 \in \mathbb{R} \Rightarrow {(a+b)x_1 \choose 0} \in \mathbb{R}^2$ (since $\mathbb{R}^2=\mathbb{R} \times \mathbb{R}$)

2. (**2nd distribuitivity law**) $\forall a \in \mathbb{R}, \forall x,y \in \mathbb{R}^2,\ a \otimes (x+y)=a \otimes x+a \otimes y \in \mathbb{R}^2$ 
$$
\begin{align}
a \otimes (x+y) &= a \otimes x+a \otimes y \\
x,y \in \mathbb{R}^2 \Rightarrow x \equiv {x_1 \choose x_2}, y \equiv {y_1 \choose y_2} &\text{ where } x_1,x_2,y_1,y_2 \in \mathbb{R} \Rightarrow\\ 
a \otimes \left( {x_1 \choose x_2} + {y_1 \choose y_2} \right) &= a \otimes {x_1 \choose x_2} + a \otimes {y_1 \choose y_2} \\
a \otimes {x_1 + y_1 \choose x_2 + y_2} &= a \otimes {x_1 \choose x_2} + a \otimes {y_1 \choose y_2} \tag{Addition of $\mathbb{R}^2$}\\
{a( x_1 + y_1) \choose 0} &= {ax_1 \choose 0} + {ax_2 \choose 0} \tag{Definition of $\otimes$}\\
{a( x_1 + y_1) \choose 0} &= {ax_1 + ay_1 \choose 0} \tag{Addition of $\mathbb{R}^2$} \\
{a( x_1 + y_1) \choose 0} &= {a( x_1 + y_1) \choose 0} \tag{Distributivity of $\mathbb{R}$} \\
&\ \checkmark
\end{align}
$$
Since $\mathbb{R}$ is closed under addition and multiplication $a( x_1 + y_1) , 0 \in \mathbb{R}^2 \Rightarrow {a( x_1 + y_1) \choose 0} \in \mathbb{R}^2$

3. (**Associativity**) $\forall a,b \in \mathbb{R}, \forall x \in \mathbb{R}^2, \ (ab)x=a(bx) \in \mathbb{R}^2$
$$
\begin{align}
(ab) \otimes x &= a \otimes ( b \otimes x) \\
x \in \mathbb{R}^2 \Rightarrow x &\equiv {x_1 \choose x_2} \text{ where } x_1 , x_2 \in \mathbb{R} \Rightarrow \\
{(ab)x_1 \choose 0} &= a \otimes {bx_1 \choose 0} \\
{(ab)x_1 \choose 0} &= { a(bx_1) \choose 0} \tag{Definition of $\otimes$} \\
{(ab)x_1 \choose 0} &= { (ab)x_1 \choose 0} \tag{Associativity of $\mathbb{R}$} \\
&\ \checkmark
\end{align}
$$
Since $\mathbb{R}$ is closed under addition and multiplication $(ab)x_1 , 0 \in \mathbb{R}^2 \Rightarrow {(ab)x_1 \choose 0} \in \mathbb{R}^2$

4. (**Identity**) $\forall x \in \mathbb{R}^2, 1 \otimes x=x \in \mathbb{R}^2$
There must exist sum $a \in \mathbb{R}$ for which the property holds
$$
\begin{align}
a \otimes x &= x \\
x \in \mathbb{R}^2 \Rightarrow x \equiv {x_1 \choose x_2} &\text{ where } x_1 , x_2 \in \mathbb{R} \Rightarrow \\
{a x_1 \choose 0 } &= {x_1 \choose x_2} \Rightarrow\\
 a=1, \ x_2&=0 \tag{1.1} \\
\Rightarrow \text{does not hold for all $x \in \mathbb{R}^2$} \\
\end{align}
$$
Counter example:
$$
\begin{align}
\text{Let $x$} = {1 \choose 1} \\
(1.1) \Rightarrow a=1 \\
\Rightarrow 1 \otimes {1 \choose 1} = {1 \choose 1}\\
{1 \choose 0} \neq {1 \choose 1} \tag{Definition of $\otimes$}
\end{align}
$$

## Exercise 2
Show that $\otimes$ (as the scalar) and $\oplus$ in $\mathbb{R}^n_{>0}$ form a vector space over $\mathbb{Q}$ where $a \otimes b \equiv (b_1^a, \dots, b_n^a)$ and $a \oplus b \equiv (a_1b_1, \dots, a_nb_n)$
$$
\begin{align}
\otimes: \mathbb{Q} \times \mathbb{R}^n_{>0} \rightarrow \mathbb{R}^n_{>0}: (a, \mathbf{b}) \mapsto a \otimes \mathbf{b}\\
\oplus : \mathbb{R}^n_{>0} \times \mathbb{R}^n_{>0} \rightarrow \mathbb{R}^n_{>0} : (\mathbf{a}, \mathbf{b}) \mapsto a \oplus b
\end{align}
$$

#### solution

1. (**1st distribuitivity law**) $\forall a,b \in \mathbb{Q}, \forall x \in \mathbb{R}^n_{>0}, \ (a \oplus b)\otimes x=a \otimes x \oplus b \otimes x \in \mathbb{R}^n_{>0}$
$$
\begin{align}
(a \oplus b)\otimes x&=a \otimes x \oplus b \otimes x \\
x \in \mathbb{R}^n_{>0} \Rightarrow x\equiv(x_1, \dots,x_n) &\text{ where } \forall i \in [n], \ x_i \in \mathbb{R}_{>0} \\
(ab) \otimes x &= (x_1^a, \dots , x_n ^a) \oplus (x_1^b, \dots , x_n^b)\\
(x_1^{ab}, \dots , x_n^{ab}) &= (x_1^ax_1^b, \dots , x_n^ax_n^b) \\
(x_1^{ab}, \dots , x_n^{ab}) &= (x_1^{ab}, \dots , x_n^{ab})\\
&\ \checkmark
\end{align}
$$
Closure 
$$
\begin{align}
\forall ab \in \mathbb{Q}, \forall x \in \mathbb{R}_{>0} \ x^{ab} &\in \mathbb{R}_{>0} \Rightarrow\\ 
(x_1^{ab}, \dots , x_n^{ab}) &\in \mathbb{R}^n_{>0} \text{ where } \forall i \in [n], \ x_i \in \mathbb{R}_{>0}
\end{align}$$

2. (**2nd distribuitivity law**) $\forall a \in \mathbb{Q}, \forall x,y \in \mathbb{R}^n_{>0},\ a \otimes (x \oplus y)=a \otimes x \oplus a \otimes y \in \mathbb{R}^n_{>0}$
$$
\begin{align}
a \otimes (x \oplus y)&=a \otimes x \oplus a \otimes y \\
x,y \in \mathbb{R}^n_{>0} \Rightarrow x \equiv(x_1, \dots,x_n), y \equiv(y_1, \dots , y_n) &\text{ where } \forall i \in [n], \ x_i,y_i \in \mathbb{R}_{>0} \\
a \otimes (x_1y_1, \dots , x_n y_n)&=(x_1^a, \dots , x_n^a)\oplus(y_1^a, \dots , y_n^a)\\
((x_1y_1)^a, \dots , (x_n y_n)^a)&=(x_1^ay_1^a, \dots , x_n^ay_n^a)\\
((x_1y_1)^a, \dots , (x_n y_n)^a)&=((x_1y_1)^a, \dots , (x_n y_n)^a) \\
&\ \checkmark 
\end{align}
$$
Closure 
$$
\begin{align}
x,y &\in \mathbb{R}_{>0} \Rightarrow 
xy \in \mathbb{R}_{>0} \\
\forall a \in \mathbb{Q}, \ \forall xy \in \mathbb{R}_{>0}, \ (xy)^{a} &\in \mathbb{R}_{>0} \Rightarrow\\ ((x_1y_1)^a, \dots , (x_ny_n)^a) &\in \mathbb{R}^n_{>0} \text{ where } \forall i \in [n], \ x_i,y_i \in \mathbb{R}_{>0}
\end{align}$$

3. (**Associativity**) $\forall a,b \in \mathbb{Q}, \forall x \in \mathbb{R}^n_{>0}, \ (a \otimes b) \otimes x=a \otimes (b \otimes x) \in \mathbb{R}^n_{>0}$
$$
\begin{align}
(a \otimes b) \otimes x &=a \otimes (b \otimes x) \\
x \in \mathbb{R}^n_{>0} \Rightarrow x\equiv(x_1, \dots,x_n) &\text{ where } \forall i \in [n], \ x_i \in \mathbb{R}_{>0} \\
(b^a)\otimes x &= a \otimes(x_1^b, \dots , x_n^b ) \\
(x_1^{b^a}, \dots , x_n^{b^a}) &=(\left(x_1^b \right)^a, \dots , \left( x_n^b \right)^a) \\
(x_1^{b^a}, \dots , x_n^{b^a}) &= (x_1^{b^a}, \dots , x_n^{b^a})\\
&\ \checkmark
\end{align}
$$
Closure
$$
\begin{align}
a,b &\in \mathbb{Q} \Rightarrow 
b^a \in \mathbb{R}\\
\forall x \in \mathbb{R}_{>0}, \ \forall b^a \in \mathbb{R}, \ x^{b^a} &\in \mathbb{R}_{>0} \Rightarrow\\
(x_1^{b^a}, \dots , x_n^{b^a}) &\in \mathbb{R}^n_{>0} \text{ where } \forall i \in [n], \ x_i \in \mathbb{R}_{>0} \text{ and } a,b \in \mathbb{Q}
\end{align}
$$

4. (**Identity**) $\forall x \in \mathbb{R}^n_{>0}, 1 \otimes x=x \in \mathbb{R}^n_{>0}$
$$
\begin{align}
1 \otimes x &= x \\
x \in \mathbb{R}^n_{>0} \Rightarrow x\equiv(x_1, \dots,x_n) &\text{ where } \forall i \in [n], \ x_i \in \mathbb{R}_{>0} \\
\Rightarrow (x_1^1, \dots,x_n^1) &=(x_1, \dots,x_n) \\
(x_1, \dots,x_n) &= (x_1, \dots,x_n) \\
&\ \checkmark
\end{align}
$$

## Exercise 3
Given $V$ is a vector space over $F$ show:
1. $\forall a \in F, \ \forall x,y \in V, \ a(x-y)=ax-ay \in V$
2. $\forall a \in F, \ \forall x \in V, (ax=0_V \Rightarrow a=0_F \cup x=0_V)$ 

#### solution

1. $\forall a \in F, \ \forall x,y \in V, \ a(x-y)=ax-ay \in V$
$$
\begin{align}
a(x-y)&=ax-ay\\
ax+a(-y)&=ax-ay \tag{2nd Distributivity Law}\\
ax+a(-y)+0_V&=ax-ay \tag{Definition of neutral element}\\
ax+a(-y)+ay-ay&=ax-ay \tag{Defintion of inverse}\\
ax+a(-y+y)-ay&=ax-ay \tag{2nd Distributivity Law}\\
ax+a0_V-ay&=ax-ay \tag{Definition of inverse}\\
ax-ay&=ax-ay \tag{Definition of neutral element}\\
&\ \checkmark
\end{align}
$$

2. $\forall a \in F, \ \forall x \in V, (ax=0_V \Rightarrow a=0_F \cup x=0_V)$

Assume the opposite $\Rightarrow \exists a \in F, \ \exists x \in V, (ax=0_V \Rightarrow a \neq 0_F \cup x \neq 0_V)$ 
which is the same as $\exists a \in F \backslash \{ 0_F \}, \ \exists x \in V \backslash \{ 0_V \}, ax=0_V$
$$
\begin{align}
\text{Let } b \in F \backslash \{ 0_F \}, \ x \in V \backslash \{ 0_V \} \\
bx-bx=0_V \tag{Definition of inverse}\\
0_V+bx-bx= 0_V \tag{Definition of neutral element}\\
ax+bx-bx= 0_V \tag{Assumption}\\
(a+b)x-bx=0_V \tag{1st Distributivity Law}\\
\text{(from assumption) } a \neq 0_F \Rightarrow a+b \neq b
\end{align}
$$

$\Rightarrow (a+b)x \text{ has two different inverses } -(a+b)x \text{ and } -bx$ 
$\text{(Prop. 1.3)} \Rightarrow \text{Contradiction, a group's element cannot have two inverse}$

## Exercise 4
Show that $V^S$ is a vector space over $F$ by checking: the additive inverse, the additive identity and 2nd distributivity law. Addition and scalar multiplication are defined  as:
$$
\begin{align}
\forall f,g \in V^S, \ \forall s \in S, \ (f+g)(s) &\equiv f(s)+g(s) \\
\forall f,g \in V^S, \ \forall s \in S, \forall a \in F, \ (af)(s) &\equiv a(f(s))
\end{align}
$$
 Note:$S$ is a set and $V$ is a vector space over a field $F$. 
 Note 2: $+$ and multiplication are the operations in vector space $V$
 
#### solutions

1. (**Additive identity**) $\forall f \in V^S, \ \forall s \in S, \ (f+\bar{0})(s)=(\bar{0}+f)(s)=f(s)$ where $\bar{0}(s)$ is the identity
$$
\begin{align}
V &\text{ is a vector space over } F \\
&\Rightarrow \exists 0_V \in V, \ \forall a \in V, a + e = e + a = a \tag{Identity existence for groups}\\
&\Rightarrow \text{Let } \forall s \in S, \bar{0}(s)=0_V \\
&\Rightarrow \bar{0}: S \rightarrow V \\
&\Rightarrow \bar{0} \in V^S
\end{align}
$$

$$
\begin{align}
(f+\bar{0})(s)=(\bar{0}+f)(s)&=f(s) \\
f(s)+\bar{0}(s)=\bar{0}(s)+f(s)&=f(s) 
\tag{Definition of +}\\
f: S \rightarrow V, \bar{0}: S \rightarrow V \Rightarrow f(s)+\bar{0}(s)&=f(s) \tag{Associativity in groups}\\
f(s)+0_V&=f(s) \tag{Definition of $\bar{0}$}\\
f: S \rightarrow V \Rightarrow f(s)&=f(s) \tag{Definition of Identity}\\
&\ \checkmark
\end{align}
$$

2. (**Additive inverse**) $\forall f \in V^S, \ \exists  g \in V^S, \ \forall s \in S, \ (f+g)(s)=\bar{0}(s)$
$$
\begin{align}
V &\text{ is a vector space over } F \\
 &\Rightarrow \forall v \in V , \exists (-v) \in V, v+(-v)=0_V \tag{Inverese existence for groups} \\
&\Rightarrow \text{Let } \forall f \in V^S, \forall s \in S, (-f)(s)=-f(s)\\
& \Rightarrow (-f): S \rightarrow V \\
& \Rightarrow (-f) \in V^S
\end{align}
$$

$$
\begin{align}
\text{Let }g&=(-f) \\
\Rightarrow (f+(-f))(s)&=\bar{0}(s) \\
f(s)+(-f)(s)&=\bar{0}(s) \tag{Definition of +}\\
\forall s \in S, f(s)-f(s)&=\bar{0}(s) \tag{Definition of $(-f)$} \\
\bar{0}(s) &=\bar{0}(s) \\
&\ \checkmark
\end{align}
$$

3. (**2nd Distributivity Law**)$\forall a \in F, \ \forall f,g \in V^S,\ \ \forall s \in S, \ (a(f+g))(s)=(af+ag)(s) \in V^S$ 
$$
\begin{align}
(a(f+g))(s)&=(af+ag)(s) \\
(a(f+g))(s)&=(af)(s)+(ag)(s) \tag{Definition of +} \\
a((f+g)(s))&=a(f(s))+a(g(s)) \tag{Definition of scalar mult.}\\
a(f(s)+g(s))&=a(f(s))+a(g(s)) \tag{Definition of +} \\
a(f(s))+a(g(s))&=a(f(s))+a(g(s)) \tag{2nd Distributivity Law for $V$}\\
&\ \checkmark
\end{align}
$$