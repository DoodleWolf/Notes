# Problem 1
## Goal
Propose a linear programming formulation for this problem.

## Givens
- $I$ is the set of nutrients
- $J$ is the set fo foods
- $a_ij$ the amount of nutrient $i$ in a unit food $j$
- $\forall (i,j) \in I \times J, \ b_i$ is the least amount of nutrient i the diet should contain
- $q_j$ the availability of food $j$
- $c_j$ is the cost of food $j$
- food $1$ cannot be more than $50$% of the total
- food $2$ atleast twice the amount of all food except 1,2,3

## Answer

$$ \text{min } f(x)=  \sum \limits_{n=1} ^{|J|} c_n x_n \text { where } x \in \mathbb{R}^{|J|}$$
such that
$$ \forall i \in I, \ \sum \limits_{n=1} ^{|J|} a_in x_n \geq b_i $$
$$ \forall j \in J, \ j \leq q_j$$
$$ x_1 \leq \frac{1}{2} \sum \limits_{n=1} ^{|J|} x_n$$
$$ \forall j \in J/\{1,2,3\}, \ x_2 \geq 2 x_j$$  
$$ x \in \mathbb{R}_+$$

# Problem 2
Propose a mathematical programming formulation to choosinmg how many pairs of each shoe to manufacture so at to max revenue

## Given
![[Pasted image 20210208172045.png]]
![[Pasted image 20210208172053.png]]
Employees must work $8 \leq x \leq 10$

## Answer
### Objective function
$$ \text{max } f(x)=56x_1 + 86 x_2 + 45x_3 + 42 x_4 + 65 x_5$$
### Constraints
$$ 
\begin{align}
x_1 & \leq 4 \\
x_2 & \leq 3 \\
x_3 & \leq 3 \\
x_4 & \leq 5 \\
x_5 & \leq 8 \\
\end{align}
$$
$y_{ij}$ is the amount of shoe type $i$ employee $j$ made 
$$
\forall i \in \mathbb{N} \leq 5, \ \sum \limits _{j=1}^3 y_{ij}=x_i
$$
$$
\begin{align}
8 & \leq 1.5y_{11} + 1.8y_{21} + 2y_{31} + 2.5y_{41} + 3.5y_{51} \leq 10 \\
8 &\leq 3.5y_{12} + 2y_{22} + y_{32} + 1.5y_{42} + 3.5y_{52} \leq 10 \\
8 & \leq 4y_{13} + 3y_{23} + 2.5y_{33} + 3.5y_{43} + 4.2y_{53} \leq 10
\end{align}
$$
### Nature of variables
$$ x \in \mathbb{Z}_{+}^5$$


# Summary
- define the sets out (e.g. employees and shoes)
- define all the needed parameters