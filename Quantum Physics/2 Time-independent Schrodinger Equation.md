# Schrodinger Equation
$$i \hbar \frac{\partial \Psi (x,t)}{\partial t}=- \frac{\hbar ^2}{2m} \frac {\partial ^2 \Psi (x,t)}{\partial x^2} + V(x)\Psi (x,t)$$
- Potential differs from problem to problem


Restrict ourselves to looking at time-independent potentials we can draw the conclusion that:
$$ \Psi (x,t) = \psi (x) \varphi(t)$$

This allows us to rewrite the equation as:

$$ i \hbar \frac {1}{\varphi (t)} \frac{\partial \varphi (t)}{\partial t} = - \frac {\hbar ^2}{2m} \frac{1}{\psi (x)} \frac{\partial ^2 \psi (x)}{\partial x^2} + V(x)$$

Since both sides depend on different variables the only solution to the equation is that both sides need to be equal to a constant defined as $E$. (not sure why?) 
![[Pasted image 20210211144638.png]]

The time equation can be solved by integrating to get the following:
## $$ \psi (t) = \psi (0) e^{\frac {i E t}{\hbar} }$$

# Important observations
### separable solutions correspond to stationary states
for wave function $\Psi (x,t)= \psi (x) \varphi (t)$ the probability density $| \Psi(x,t)|^2$ is time independent
![[Pasted image 20210211170623.png]]


### separable solutions have definite energy
![[Pasted image 20210211170756.png]]
![[Pasted image 20210211170852.png]]

### general solution is a linear combination of seperable solutions
![[Pasted image 20210211171154.png]]

## Recipe for solving the time-independent SE
![[Pasted image 20210211171340.png]]
