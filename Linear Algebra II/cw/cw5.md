# Linear Algebra II (MATH1049)
# Coursework 5

## Exercise 1
Which of the following span the vector space $\mathbb{P}_2$?
1.  $U= \{\frac 12, t^2+t, t^2-1 \}$
2.  $V= \{1, 2t, t^2, 3t^2+5 \}$
3.  $W= \{t+1,t^2+t \}$

### Solution
1. $U$ is a spanning set of $\mathbb{P}_2$

-  Proof of $\operatorname{Span}(U) \subset \mathbb{P}_2$
Since $\frac 12, t^2+t, t^2-1 \in \operatorname{Span}(\{ t^0,t^1,t^2 \})$ it follows that $\operatorname{Span} (U) \subset \mathbb{P}_2$

- Proof of  $\mathbb{P}_2 \subset \operatorname{Span}(U)$
$$
\begin{align}
t^0 &= 2 \cdot \frac 12 \\
t^1 &= (t^2+t)+ (-1)\cdot(t^2-1)+(-2)\cdot \frac 12 \\
t^2 &= (t^2 - 1)+2 \cdot \frac 12 \\
&\Rightarrow \{ t^0, t^1, t^2 \} \subset \operatorname{Span}(U) \Rightarrow \mathbb{P}_2 \subset \operatorname{Span}(U)
\end{align}
$$

$\Rightarrow  \mathbb{P}_2 =  \operatorname{Span}(U)$

2. $V$ is a spanning set of $\mathbb{P}_2$

- Proof of $\operatorname{Span}(V) \subset \mathbb{P}_2$
Since $V \subset \operatorname{Span}(\{ t^0,t^1,t^2 \})$ it follows that $\operatorname{Span}(V) \subset \mathbb{P}_2$

- Proof of $\mathbb{P}_2 \subset \operatorname{Span}(V)$
$$
\begin{align}
t^0 &\in V \\
t^1 &= \frac12 \cdot 2t \\
t^2 &\in V \\
&\Rightarrow \{ t^0, t^1, t^2 \} \subset \operatorname{Span}(V) \Rightarrow \mathbb{P}_2 \subset \operatorname{Span}(V)
\end{align}
$$

$\Rightarrow \mathbb{P}_2 = \operatorname{Span}(V)$

3. $W$ is  not a spanning set of $\mathbb{P}_2$
Assume the opposite: $\operatorname{Span}(W)= \mathbb{P}_2$
$$
\begin{align}
\Rightarrow \exists a_0, a_1 \in \mathbb{R}, \ a_0(t+1)+a_1(t^2+t)=t^0 \\
a_1t^2+(a_0+a_1)t+a_0=1 \\
\text{Since the RHS has no $t^2$} \Rightarrow a_1=0 \\
\Rightarrow a_0t=1 \\
\text{Contradiction}
\end{align}
$$

## Exercise 2
Which of the following are linearly independent?
1. $U=\{ 1 +t, \ 1+t+t^2, \ 1+t+t^2+t^3, \ 1+t+t^2+t^4 \}$
2. $V=\{ \sin , \ \cos^2 , \ \sin^3  \}$
3. $W=\{ 1 , \  \sin^2 , \ \cos^2 \}$

### Solution
1. $U$ is linearly independent
Assume the opposite: $U$ is linearly dependent
$$
\begin{align}
\Rightarrow \exists a_0 , a_1 , a_2, a_3 \in \mathbb{R}, a_0(1+t)+a_1(1+t+t^2)+a_2(1+t^2+t^3)+a_3(1+t+t^2+t^4)=0 \\
a_3t^4+a_2t^3+(a_1+a_2+a_3)t^2+(a_0+a_1+a_3)t^+(a_0+a_1+a_2+a_3)=0\\
\text{Since the RHS has no $t^4$} \Rightarrow a_3=0 \\
\Rightarrow a_2t^3+(a_1+a_2)t^2+(a_0+a_1)t+(a_0+a_1+a_2)=0 \\
\text{Since the RHS has no $t^3$} \Rightarrow a_2=0 \\
\Rightarrow a_1t^2+(a_0+a_1)t+(a_0+a_1+a_2)=0\\
\text{Since the RHS has no $t^2$} \Rightarrow a_1=0 \\
\Rightarrow a_1t+(a_0+a_1)=0 \\
(\dots) \Rightarrow a_1,a_0=0 \\
\text{Contradiction as not all $a$ can be equal to 0}
\end{align}
$$

2. $V$ is linearly independent
Assume the opposite: $V$ is linearly dependent
$$
\begin{align}
\Rightarrow \exists a_0 , a_1 , a_2 \in \mathbb{R}, \ a_0 \sin x + a_1 \cos ^2 x + a_2 \sin ^3 x =0 \\
a_0 \sin x + a_1 \ cos^2 x + a_2( \sin x - \sin x \cos^2 x) =0\\
(a_0+a_2) \sin x+\cos^2 x (a_1 - a_2 \sin x)=0 \\
\text{Since the RHS has no $\sin x$} \Rightarrow a_0=-a_2 \\
\Rightarrow \cos^2x(a_1+a_0 \sin x)=0 \\
\forall x \in \mathbb{R}, \cos^2x \neq 0 \Rightarrow a_1+a_0 \sin x=0\\
\text{Since the RHS has no $\sin x$} \Rightarrow a_0=0\\
\Rightarrow a_1=0 \\
\text{Contradiction as not all $a$ can be equal to 0}
\end{align}
$$

3. W is linearly dependent
$\sin ^ 2 x + \cos^2x=1$

## Exercise 3
Find the basis and dimension of $N(A) \subset \mathbb{R}^5$ where
$$
A = 
\begin{pmatrix}
1 & -3 & 3 & -1 & -1 \\ 
-2 & 6 & -1 & -3 & -8 \\
3 & -9 & 10 & -4 & -5 
\end{pmatrix}
\in M_{3 \times 5} (\mathbb{R})
$$

### Solution
Solving for $N(A): A \mathbf{x}=0$
$$
\begin{align}
\left(
\begin{array}{ccccc|c}
1 & -3 & 3 & -1 & -1 & 0 \\ 
-2 & 6 & -1 & -3 & -8 & 0\\
3 & -9 & 10 & -4 & -5 & 0
\end{array}
\right)
\overset{\begin{align}
R_2 \rightarrow R_2 + 2R_1\\
R_3 \rightarrow R_3 - 3R_1
\end{align}
}{\longrightarrow}
\left(
\begin{array}{ccccc|c}
1 & -3 & 3 & -1 & -1 & 0 \\ 
0 & 0 & 5 & -5 & -10 & 0 \\
0 & 0 & 1 & 1 & -2 & 0
\end{array} 
\right) \\
\overset{R_2 \leftrightarrow R_3}{\longrightarrow}
\left(
\begin{array}{ccccc|c}
1 & -3 & 3 & -1 & -1 & 0 \\ 
0 & 0 & 1 & 1 & -2 & 0\\
0 & 0 & 5 & -5 & -10 & 0
\end{array} 
\right)
\overset{\begin{align}
R_1 \rightarrow R_1 - 3R_2\\
R_3 \rightarrow R_3 - 5R_2
\end{align}
}{\longrightarrow}
\left(
\begin{array}{ccccc|c}
1 & -3 & 0 & -4 & 5 & 0 \\ 
0 & 0 & 1 & 1 & -2 & 0\\
0 & 0 & 0 & -10 & 0 & 0
\end{array} 
\right) \\
\overset{R_3 \rightarrow -\frac{1}{10}R_3}{\longrightarrow}
\left(
\begin{array}{ccccc|c}
1 & -3 & 0 & -4 & 5 & 0 \\ 
0 & 0 & 1 & 1 & -2 & 0\\
0 & 0 & 0 & 1 & 0 & 0
\end{array} 
\right)
\overset{\begin{align}
R_1 \rightarrow R_1 + 4R_3\\
R_2 \rightarrow R_2 - R_3
\end{align}
}{\longrightarrow}
\left(
\begin{array}{ccccc|c}
1 & -3 & 0 & 0 & 5 & 0 \\ 
0 & 0 & 1 & 0 & -2 & 0\\
0 & 0 & 0 & 1 & 0 & 0
\end{array} 
\right)\\
\end{align}
$$
$$
\begin{align}
\begin{cases}
x_1-3x_2+5x_5=0 \\
x_3-2x_5=0 \\
x_4=0
\end{cases} 
\quad
\begin{cases}
x_1=3x_2-5x_5 \\
x_3=2x_5\\
x_4=0
\end{cases} \\
\end{align}
$$
$$
\text{Let } x_5=u, x_2=v \text{ hence } N(A)= 
\{u,v \in \mathbb{R}: 
\begin{pmatrix}
3v-5u \\
v \\
2u \\
0 \\
u
\end{pmatrix}
\} 
$$
$$
\text{Basis of $N(A)$ is }
\begin{pmatrix}
3 \\
1 \\
0 \\
0 \\
0
\end{pmatrix},
\begin{pmatrix}
-5 \\
0 \\
2 \\
0 \\
1
\end{pmatrix}
\text{ the dimension of $N(A)$ is 2}
$$

## Exercise 4
1. Do the following matrices form a basis of $M_{2 \times 2}(\mathbb{R})$

$$
\begin{align}
A_1 =
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
\qquad
A_2 = 
\begin{pmatrix}
2 & 1 \\
0 & 0
\end{pmatrix}
\qquad
A_3 = 
\begin{pmatrix}
3 & 2 \\
1 & 0
\end{pmatrix}
\qquad
A_4 = 
\begin{pmatrix}
4 & 3 \\
2 & 1
\end{pmatrix}
\end{align}
$$

2. Find the basis and dimension of $W = \{ A \in M_{2 \times 2}(\mathbb{R}) | \operatorname{trace}(A)=0 \}$

### Solution
1. $A_1, A_2, A_3, A_4$ form a basis of $M_{2 \times 2}(\mathbb{R})$
- $A_1, A_2, A_3, A_4$ are linearly independent
Assume the opposite:
$$
\begin{align}
\exists a_1, a_2, a_3, a_4 \in \mathbb{R}, a_1A_1+a_2A_2+a_3A_3+a_4A_4=0_{2\times2} \\
\begin{pmatrix}
a_1+2a_2+3a_3+4a_4 & a_2+2a_3+3a_4 \\
a_3+2a_4 & a_4
\end{pmatrix} =
\begin{pmatrix}
0 & 0 \\
0 & 0
\end{pmatrix}\\
\Rightarrow a_4 = 0 \Rightarrow \begin{pmatrix}
a_1+2a_2+3a_3 & a_2+2a_3 \\
a_3 & 0
\end{pmatrix} =
\begin{pmatrix}
0 & 0 \\
0 & 0
\end{pmatrix} \\
\Rightarrow a_3 = 0 \Rightarrow \begin{pmatrix}
a_1+2a_2& a_2\\
0 & 0
\end{pmatrix} =
\begin{pmatrix}
0 & 0 \\
0 & 0
\end{pmatrix} \\
\Rightarrow a_2 = 0 \Rightarrow \begin{pmatrix}
a_1& 0\\
0 & 0
\end{pmatrix} =
\begin{pmatrix}
0 & 0 \\
0 & 0
\end{pmatrix} \\
a_1=0 \\
\text{Contradiction as not all $a$ can be equal to 0}
\end{align}
$$
- $\operatorname{Span}(A_1, A_2, A_3, A_4) = M_{2 \times 2}(\mathbb{R})$
	- $\operatorname{Span}(A_1, A_2, A_3, A_4) \subset M_{2 \times 2}(\mathbb{R})$
		Since matrix addition and scalar multiplication is closed in that matrix size it follows that $\operatorname{Span}(A_1, A_2, A_3, A_4) \subset M_{2 \times 2}(\mathbb{R})$
	- $M_{2 \times 2}(\mathbb{R}) \subset \operatorname{Span}(A_1, A_2, A_3, A_4)$

$$
\begin{align}
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} &= A_1 \\
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix} &= -2A_1+A_1 \\
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix} &= A_1-2A_1+A_3 \\
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix} &= A_2-2A_3+A_4 \\
\operatorname{Span}(\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix},
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix},
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix},
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}) &\subset \operatorname{Span}(A_1,A_2,A_3,A_4) \\
\Rightarrow M_{2 \times 2}(\mathbb{R}) &\subset \operatorname{Span}(A_1,A_2,A_3,A_4)
\end{align}
$$
2. Finding the basis and dimension of $W$
$$
\begin{align}
\forall A \in W, \ \operatorname{trace}(A)=0 \\
\forall A \in W, \ A= 
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix} \text{ where } a+d=0 \Rightarrow d=-a \quad (a,b,c,d \in \mathbb{R})\\
\forall A \in W, A =
\begin{pmatrix}
a& b \\
c & -a 
\end{pmatrix}=
a \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
+b
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
+c
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix} \\
\Rightarrow \operatorname{Span}( \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
,
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
,
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix})=W \\
\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
,
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
,
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix} \text{ are linearly independent as none share an element in any spot} \\
\Rightarrow \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
,
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
,
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix} \text{ form a basis of $W$ hence $\operatorname{dim}(W)=3$}
\end{align}
$$