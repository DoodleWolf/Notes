# 1 problem
## problem statement
Find + sketch domain of $f(x,y)= \frac{\sqrt{x^2+y^2-9}}{x}$

## solving
Looking for domain:
- from square root=> $x^2+y^2-9 \geq 0$ => $x^2=y^2 \geq 9$ (circle of radius 3)
- form fraction => $x \neq 0$

## answer
![[Pasted image 20210208191130.png]]
$$ D={(x,y) \in \mathbb{R}^2 | x^2+y^2 \geq 9 \cap x \neq 0} $$

# 2 problem
## problem statement
Find + sketch domain $f(x,yz)= \frac{x}{\sqrt{16-x^2-y^2-z^2}}$

## solving
Looking for domain:
- from square root => $16-x^2-y^2-z^2>0$ => $x^2+y^2+z^2 < 16$ (sphere of radius 4)

## answer
![[Pasted image 20210208191500.png]]
$$D={(x,y,z) \in \mathbb{R}^3 | x^2+y^2+z^2 < 16}$$

# 3 problem
## problem statement
Find domain + range $f(x,y)=x \sqrt{y}$

## solving
Looking for domain
- from square root => $y \geq 0$
- $x$ has no restriction so $f$ is defined $\forall x$

Looking for range:
- $\sqrt{y} \leq 0$
- $- \infty < x < + \infty$
hence $- \infty < f(x,y) < + \infty$


## solution
$$D = {(x,y) \in \mathbb{R}^2 | y \geq 0} $$
$$R= (-\infty,+\infty )$$

# 4 problem
## problem statement
Find domain and range of $f(x,y)= e^{x+y}$

## solving
Recall domain and range for $e^u$
- $R=\mathbb{R}$ (range)
- $D=(0, \infty )$

Clearly $- \infty < x+y < \infty$

## answer
$$D= \{(x,y) \in \mathbb{R}^2 \}$$
$$R = {f \in \mathbb{R} | f>0}$$

# 5 problem

## problem statement
Sketch and fInd contour lines of $z=8-4x-2y$

## solving
Contours: $c=8-4x-2y$ where $c$ is a constant
$$y=4-2x- \frac c2=-2x+ \frac{8-c}{2}$$
=> Gradient $-2x$ and intercept $\frac{8-c}{2}$
![[Pasted image 20210208192905.png]]

Note: from linear algebra we know this is a plane 
Drawing plane
1. solve for a single variable by setting the others to $0$
![[Pasted image 20210208193125.png]]
2. Draw in countour lines (not necessary)
![[Pasted image 20210208193303.png]]

## solution
Countours: 
$y=-2x+ \frac{8-c}{2}$
![[Pasted image 20210208192905.png]]

Sketch:
![[Pasted image 20210208193125.png]]

# 6 problem
## problem statement
sketch contours of $f(x,y)=xy$

## solving 
Contours: $c=xy$ where $c$ is a constant => $y = \frac cx,  \ c \neq 0$
![[Pasted image 20210208193756.png]]

consider $c=0$ case
![[Pasted image 20210208193917.png]]

## solution
![[Pasted image 20210208193917.png]]

# 7 problem

## problem statement
sketch contours of $f(x,y)=ln(xy)$

## solving 
Contours: $c=ln(xy)$ where $c$ is a constant => $xy=e^c$

- $ln > 0 => xy>0$ , recall function $lnu$
![[Pasted image 20210208194317.png]]

recall $xy$ case:
![[Pasted image 20210208194606.png]]
the contour lines would look like this but it you'd take into account that the lines represent $e^c$

wolfram:
![[Pasted image 20210208194814.png]]

## solution
![[Pasted image 20210208194606.png]]