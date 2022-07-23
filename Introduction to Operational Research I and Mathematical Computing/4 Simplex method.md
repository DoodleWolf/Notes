## 4.1 Definition (basic matrix)
$A_B$ is a called a basic matrix if it's a submatrix of $A \in M_{n \times n}(\mathbb{R})$  with linearly independent columns (not rows!) where the index of the each column is in $B$
- $B \subset [n]$ with $|B|=m$
- $A_n$ is the complement matrix ($N = [n]\B$)
- $A = (A_B, A_N)$

## 4.2 Definition (basic form of an LP)
![[Pasted image 20210414155828.png]]

### proof 
$$
Ax = b \quad \Leftrightarrow \quad A_Bx_B+A_Nx_N=b \quad \Leftrightarrow \quad x_B=A_B^{-1}b-A_B^{-1}A_Nx_N
$$

$$
\begin{align}
cx &= c_Bx_B+c_Nx_N \\
&= c_BA_B^{-1}b+(c_N-c_BA_B^{-1}A_N)x_N \\
&= c_BA_B^{-1}b+(c_N-c_BA_B^{-1}A_N)x_N + (c_B - c_BA_B^{-1}A_B)x_B 
\end{align}
$$

## 4.3 Definition (basic and non-basic variables)
In the basic form, $x_B$ are the basic variables and $x_N$ are the non-basic variables

## 4.4 Definition ( (feasible) basic solution)
A basic solution is one where $x_N=0$ and $x_B=A_B^{-1}b$.
A basic feasible solution is a basic solution where $x_B \geq 0$.

## 4.5 Theorem
$x$ is a basic feasible solution iff $x$ is a vertex

## 4.6 Definition (vectors of reduced cost)
- vector of the reduced costs of the non-basic variables
$\bar c _N = c_N - c_B A_B^{-1}A_N$
- vector of the reduced costs of the basic variables
$\bar c _B =  c_B - c_BA^{-1}A_B=0$
- vector of the reduced costs
$\bar c = c-c_BA_B^{-1}A=( \bar c _B, \bar c _N)$

## 4.7 Theorem (Optimality test)
if $x$ is a basic feasible solution with basis $B$ and $\bar c \geq 0$ $\Rightarrow$ $x$ is optimal

### proof
- show that any other feasible solution is $cy \geq cx$
- consider $d=y-x$
- can be shown that $d=(d_B, d_N)=(cd_N, d_N)$
- since $y_N \geq 0$ $d_N=y_N-x_N \geq 0$ (since $x_N=0$)

## 4.8 Proposition (minimum ratio test)
To move to an adjacent solution find  an $s \in N$ where $\bar c_s < 0$ then let
$$
x_s = \underset{i \in B, \bar a_{is} >0}{\min} \left( \frac{\bar b_i}{\bar a_{is}} \right)
$$
then through the resulting $x_{B_i}$ from the $\min$ into the nonbasic variables (as it should equal zero)

## 4.9 Algorithm (simplex method)
![[Pasted image 20210422135737.png]]

Notes:
- $B := (B \backslash \{ r \}) \cup \{ s \}$

