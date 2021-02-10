# Modeling

## Graphical view
Complex model of modeling:
![[Pasted image 20210205134533.png]]

Simple model of modeling:
![[Pasted image 20210205130838.png]]

### Assumptions 
- Newtonian physics 
- Relativity

### Formulations
- simplify with symmetries, variables
- use conservatons laws
- Newton's laws (Lagrangian variation principle)

# Newton's laws

1. A body remains at rest or in uniform motion with respect to an inertial frame unless acted upon by a net force 
	- ,ie, a body in motion stays in motion
2. In an inertial frame a body acted upon by a net force moves in such a way that the rate of change with time of momentum equals the net force applied
3. If two bodies exert net forces upon each other, these net forces are equal in magnitude and opposite in direction.


**mass** - $m$ - physical qunatity associated with the that resists motion
**momentum** - $\overrightarrow{p}$

## Cartesian coordinates
![[Pasted image 20210205132149.png]]
$$ \overrightarrow{r} (t) = x (t) \hat{i} + y (t) \hat{j} + z (t) \hat{k}$$

### unit vectors
![[Pasted image 20210205134657.png]]

### Rate of change
$$\overrightarrow{v} (t) = \lim _{\delta t \rightarrow 0} \frac{\overrightarrow{r}(t + \delta t) - \overrightarrow{r} (t)}{\delta t} $$
![[Pasted image 20210205132507.png]]

## Newton's 2nd Law
"the sum of the forces is the change in time of momentum" =>
$$\vec{F} \equiv \frac{d \vec{p}}{dt} = \frac{d(m \vec{v})}{dt} = \frac{dm}{dt} \vec{v} + m \frac{d \overrightarrow{v}}{dt}= \frac{dm}{dt} \dot{\vec{r}} + m \ddot{\vec{r}}$$
hence
$$\vec{F} \equiv \frac{dm}{dt} \dot{\vec{r}} + m \ddot{\vec{r}}$$

# First order ODEs
## Seperable equations
Where one can seperate the variables in the equation

### Example
![[Pasted image 20210205133440.png]]

## Linear equations
Look like:
![[Pasted image 20210205133615.png]]
1. Find integrating factor
![[Pasted image 20210205133727.png]]
2. Solve
![[Pasted image 20210205133753.png]]

