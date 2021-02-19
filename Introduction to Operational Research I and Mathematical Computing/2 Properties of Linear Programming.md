# Two main forms of LPs (+1)

## Canonical form
![[Pasted image 20210210145501.png]]
Matrix notation:
![[Pasted image 20210210145537.png]]
![[Pasted image 20210210150453.png]]

## Standard form
![[Pasted image 20210210145507.png]]
![[Pasted image 20210210150459.png]]

## Simplified canonical form
![[Pasted image 20210210150428.png]]


# Transformation rules
1. swap between min and max problems
$$\operatorname{max}(xc) \Rightarrow - \operatorname{min}(-cx)$$
2. change inequality direction
$$ ax \leq b \Rightarrow -ax \geq - b$$
3. swap between inequalities and equalities
$$ ax=b \Rightarrow ax \leq b \text{ and } ax \geq b$$
4. $\leq$ inequality into equation
$$ ax \leq b \Rightarrow ax+s=b \text{ where } s \geq 0$$
5. $\geq$ inequality into equation
$$ ax \geq b \Rightarrow ax-s=b \text{ where } s \geq 0$$
6. turn variables into sign restricted variables
![[Pasted image 20210210150159.png]]

## Standard form conversion example
![[Pasted image 20210210150302.png]]
![[Pasted image 20210210151259.png]]


# Geometrical inequalities

 - **Halfspace** : $\{ x \in \mathbb{R}^n | a_i x \leq b_i \}$
 - **Hyperplane** : $\{ x \in \mathbb{R}^n | a_i x  = b \}$ (the constraint $a_i x \leq b_i$ is tight/binding for the hyperplane)
 
 Notes:
 - $a_i$ is orthogonal to the hyperplane
 - $a_i$ points away from halfspace ($\leq$)

## Polyhedra
**Polyhedra** : the intersection of a finite number of halfspaces
![[Pasted image 20210210152511.png]]

The feasible region of LP in simplified canonical form
![[Pasted image 20210210151956.png]]
or $P= \{ x \in \mathbb{R}^n | Ax \leq b \}$

Is obtained by intersecting halfspaces of type
$$ \{ x \in \mathbb{R}^n | ax_i \leq b_i \}$$


## Convex 

**Convex combinations of points**:
The **convex combinations of** $x_1, \dots , x_k \in \mathbb{R}^n$
$$
\forall \sum \limits ^k _{i=1} \lambda_i = 1 \text{ where } \lambda_i \geq 0, \ y= \sum \limits ^{k} _{i=1} \lambda _i x_i \text{ where } x_i \in \mathbb{R}^n
$$

**Convex set**:
$S \subset \mathbb{R}^n$ is **convex**
$$
\forall x_1, x_2 \in S, \forall \lambda \in [0,1], \ y= \lambda x_1 + (1- \lambda ) x_2 \in S
$$
i.e., if it contains all convex combinations of its elements

![[Pasted image 20210217213847.png]]

## Vertices, faces and facets

**vertex**: a point $v$ in a polyhedron $P$ which cannot be expressed as a convex combination of two other points $x,y \in P$ where $x \neq y \neq v$

**face**: a planar surface on the boundary of a polyhedron

**facet**: n-1 dimensional face

![[Pasted image 20210217214341.png]]


## Conic Combinations

The **conic combinations** of points $x_1, \dots x_k \in \mathbb{R}^n$ are
$$
forall \mu \geq 0, \ y= \sum \limits ^h _{i=1} \mu_i x_i
$$

## Rays

**Ray**: $r \in \mathbb{R}^n$ is a ray if
$$ \forall x_0 \in S, \forall \mu \geq 0, \ x_0 + \mu r \in S$$

**extreme ray**: $r$ is an extreme ray if it cannot be expressed as a conic combination of two distinct rays

## Boundedness

**bounded**: set $S$ if
$$
\forall x \in S, \exists \delta \geq 0 , \ ||x||_2 \leq 0
$$
Note: the convergence of $p$-norms in $\mathbb{R}^n$ means that any $||.||_p$ can be used

**polytope**: bounded polyhedron

## Wey-Minkowski theorem

#### Theorem

P is a nonempty polyhedron $\Leftrightarrow$  $x \in P$ can be written as a convex comb. of vertices plus a conic comb. of the extreme rays

$$
\begin{align}
x \in P \Rightarrow \exists (\lambda)_{n=1}^k \geq 0 \text{ s.t. } \sum \limits_{i=1} \lambda_i=1, \exists (\mu)_{i=1}^h \geq 0, \\
x= \sum \limits_{i=1}^k \lambda_i v_i + \sum \limits_{i=1}^h \mu_i r_i \qquad
\end{align}
$$
$(v)_{i=1}^k$: the set of vertices
$(r)_{i=1}^k$: the set of extreme rays

# Fundamental theorem of linear programming

$P = \{ x \in \mathbb{R}^n : Ax \leq b\}$
Linear programing problem: $\max \{cx : x \in P \}$

=> there is either an optimal solution $x^*$ corresponding to one of its vertices or it is unbounded

### proof
[[^Wey | Wey-Minkowski theorem]] 
$$\Rightarrow \left( x\in P \Rightarrow x= \sum \limits_{i=1}^k \lambda_i v_i + \sum \limits_{i=1}^k \mu_i r_i \right)$$
Let $x \in P$  then the objective function becomes
$$cx = c \left( \sum \limits_{i=1}^k \lambda_i v_i + \sum \limits_{i=1}^k \mu_i r_i \right)=\sum \limits_{i=1}^k c \lambda_i v_i+\sum \limits_{i=1}^k c \mu_i r_i$$
constraints:
$$
\begin{align}
(\lambda)_{i=1}^k \geq 0 \\
\sum \limits_{i=1}^k \lambda_i = 1 \\
(\mu)_{i=1}^k \geq 0
\end{align}
$$
Our linear programming problem has turned into
![[Pasted image 20210218123113.png]]
if $cr_i$ is not $\leq 0$ then since $(\mu)_{i=1}^k$ is not bounded LP is unbounded, hence
LP is bounded => $cr_i \leq 0$ hence the max would be if the sum went to $0$
$$
\Rightarrow cx^*=\sum \limits_{i=1}^k \lambda_i c v_i \Rightarrow cx^*=\max_{i=1,\dots,k} \{ cv_i \}
$$

## non-optimal interior

$x \in P$ interior then it cannot be optimal

#### proof

since $x$ is in the interior it must be able to move in the direction of the gradient hence it is not optimal

## Four types of linear programs

![[Pasted image 20210218125936.png]]

**bounded LP**: if it admits a finite optimal solution

## Enumaration inefficient
number of vertices given $n$ variables and $m$ inequalities:

$$m \choose n$$