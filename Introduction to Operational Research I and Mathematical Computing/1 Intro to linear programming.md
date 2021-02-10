# Mathematical programming problems

## Decision-making problem structure
![[Pasted image 20210208110240.png]]
- feasible region: ${x \in X: g_i (x) [\leq | \geq | =]_i b_i}$ (where $[a|b|c]$ means a or b or c): possible solutions
- decision variables: $x$: answer variables
- objective function: $f(x)$: cost/profit function (that's what the min|max stands -> min if cost)
- constraints: $g_i (x) [ \leq | \geq | =]_i b_i$: imposing properties that define possible solution
- Nature of the variables: $X$: could bew $\mathbb{R}$ or $\mathbb{Z}^n$

# Local and global optima
## Local optimum
$x^*$ is a locally optimal solution if it is feasible and:
$$\exists \epsilon >0, ||x-x^*||\leq \epsilon \Rightarrow f(x^*)[\leq \text { (min prob.)} | \geq \text { (max prob.)} ] f(x)$$

## Global optimum
$x^*$ is a gobally optimal solution if it's feasible and:
$$\forall \text{ feasible } x, \ f(x^*) [\leq | \geq ] f(x)$$


# Linear programming problem (LPs)
The mathematical programming is linear if:
1. $f(x)$ is linear
2. $g_i (x)$ is linear
3. $X= \mathbb{R}^n$

![[Pasted image 20210208161845.png]]

## Example
![[Pasted image 20210208162401.png]]
![[Pasted image 20210208162414.png]]
![[Pasted image 20210208162420.png]]
![[Pasted image 20210208162427.png]]

### Variables:
$x_B , x_M , x_E \geq 0$ Bread, Milk, Egg amount

### Constraints
min carbs: $300 x_B + 30 x_M + 20 x_E \geq 300$
min proteins: $5 x_B + 50 x_M + 90 x_E \geq 600$
min vitamins: $0.07 x_B + 0.02 x_M + 0.12 x_E \geq 1$

### Objective function
min cost $f$ : $2.5 x_B + 1.2 x_M + 0.8 x_E$

### Nature of variables
$x_B, x_M, x_E \geq 0$

### Extra info
The diet problem is the first large-size linear programming problem. (G. Steigler solved for 77 foods and 9 nutrients)

# Optimal transportation
The problem considersr there being nodes on the right and nodes on the left. The nodes on the left have certain given values $\mu_i$ ($i$th left node), which must get divided up to the nodes on the right we have the values $v_i$ ($i$th right node).
![[Pasted image 20210210121245.png]]
![[Pasted image 20210210120945.png]]
![[Pasted image 20210210120958.png]]

## General formulation
![[Pasted image 20210210121307.png]]
where $x_{ij}$ stands for the the value given from $\mu_i$ to $v_j$

## Application
- used in probability where $\mu$ and $v$ are distributions and the optimal solution value of the problem measures their distance (Wasserstein distance of order 2)

# Optimal portfolio
Given a sum of money to invest and a set of portfolios with certain percentile profit, and a set of constraints for how much can be added to these portfolios, what is the best way to spread the investment on the portfolios

# Graphical solution (only works for 2 portfolios)
1. Draw the feasible region (ie all constraints)
2. Draw the gradient of the objective function
3. Draw it's level curves (orthogonal lines to the gradient)
4. Find the farthest possible level curve which stays in the feasible region (the points in the feasible region are the optimal solutions)