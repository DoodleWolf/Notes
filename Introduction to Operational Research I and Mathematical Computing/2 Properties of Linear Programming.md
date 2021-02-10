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

