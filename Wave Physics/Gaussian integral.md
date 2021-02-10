# Gaussian integral
![[Pasted image 20210128163553.png]]
gaussian pulse graphically ($e^{-x^2}$)
![[Pasted image 20210128170838.png]]

### First we solve the gaussian integral (itll be usefull later)
1. we square
![[Pasted image 20210128163627.png]]
2.  we can think of this in polar coords.
	- $\operatorname{dA}=\operatorname{dx}\operatorname{dy}$
	-  $\operatorname{dA}=r \operatorname{dr} \operatorname{d \theta}$
		 ![[Pasted image 20210128164612.png]]
3. solve for polar
![[Pasted image 20210128163748.png]]
4. now just square root
![[Pasted image 20210128164649.png]]


### Solve for coefficients
1. we know it's gaussian (of width $x_{0}$)
![[Pasted image 20210128165637.png]]
2. since it's symmetric, $\cos$ will be used
![[Pasted image 20210128165735.png]]
3. replace $\cos$ with it's complex form $\frac {e^{ix}+e^{-ix}{2}$
![[Pasted image 20210128165900.png]]
4. adding opposite exponentials over $\plusminus \infty$ is like adding one doubled
![[Pasted image 20210128165957.png]]
5. complete the square so that we get our gaussian integral and then we just solve
![[Pasted image 20210128170046.png]]

### Normalize
1. plug our coeff. into our $\psi (x)$
![[Pasted image 20210128170432.png]]
2. Normalize
![[Pasted image 20210128170516.png]]
3. normalized gaussian
![[Pasted image 20210128170549.png]]

### Gaussian Wavepacket
gaussian pulse but with a sinusoidal multiplied (and centered at $k_{1}$)
![[Pasted image 20210128171200.png]]
the [[Fourier Principle#^9f72bf | alternative approach]] of taking the real part of a complex wave is used for this variation

## Bandwidth theorem
![[Pasted image 20210128171646.png]]
- as one increases the frequency the period decreases
![[Pasted image 20210128171713.png]]
![[Pasted image 20210128171726.png]]

The difference in Hz that can be noticed for the pulse duration (ie so you wouldn't notice a difference of 100Hz if it was played for ~0.001 sec):
![[Pasted image 20210128171914.png]]

### Dirac - $\delta$ function
(helps us define our completeness)
![[Pasted image 20210128172539.png]]
![[Pasted image 20210128172522.png]]

Can also be written as:
![[Pasted image 20210128172810.png]]
why we can add $sin$:
- since at when $k=0$ the $sin$ will vanish
- and $sin$ is an odd function so over a symmetrical integral it will be $0$ 

## Completeness
We can make any $f(x)$ out of $\delta (x)$
![[Pasted image 20210128173754.png]]
we have given a definitive answer to what $g(x)$ is and we know that our $\delta (x)$ can be expressed in such a way as well, showing that any function can be made like that, therefore that such a form is complete.

umm also it appears we just take the integral to be unity with no other explanation:
![[Pasted image 20210128175531.png]]