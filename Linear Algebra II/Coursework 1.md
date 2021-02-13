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

