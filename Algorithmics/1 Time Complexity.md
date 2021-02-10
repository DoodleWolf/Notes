## Travelling Salesman Problem
Given a set of distances between destination find the shortest destination between two distances
### Brute Force
Given $n$ cities there are $(n-1)!$ tours but since direction doesn't count $(n-1)!/2$


# Sorting
![[Pasted image 20210204162059.png]]

## Running Time
Count the number of elementary operations (abstracting from hardware)
=> elementary operations take a fixed time to execute

### Input Size
Running time can depend on input
size is problem-dependent:
- array size
- number of cities
- nodes/edges in graph

### Cases in running time
The worst-case is a function $T : \mathbb{N} \rightarrow \mathbb{N}$ where $T(n)$ is the max number of elementary operations the algorithm can use on an input of size $n$
(average-case reutrns the average number of elem. oper.)

![[Pasted image 20210204163645.png]]
(not sure what exactly is getting graphed)
![[Pasted image 20210204163831.png]]

## Example: minimum element in an array
![[Pasted image 20210203133402.png]]


# Rates of Growth
We're interested in what happens when the input get very large

## Big-$\Theta$ notation (informally)
Meant to show that two functions have the same rate of growth

### Definition 
$f(n)$ is $\Theta (g(n))$ when $f(n) \approx cg(n)$ for $n \gg 1$ for some constant $c>0$

### Cons
- bad for small input analysis
- cannot compare algorithms whose complexities have the same rate of growth (?)

### Counting Operations
Assuming no **if** statement is found then worst=average=best

# Bounds
Upper bound: Big-O notation $O(f)$
Lower bound: Big-Omega notation $\Omega (f)$
![[Pasted image 20210204173556.png]]

# Precise Definition
## Big-O Notation
$f(n)$ is $O(g(n))$ if 
$$\exists c>0, \ \exists N \in \mathbb{N}, \ \forall n \geq N, \ f(n) \leq cg(n)$$

A multiple of the function can be found to bound it above.

## Big-$\Omega$ Notation
$f(n)$ is $\Omega (g(n))$ if
$$\exists c>0, \ \exists N \in \mathbb{N}, \ \forall n \geq N, \ f(n) \geq cg(n)$$

A multiple of the function can be found to bound it below.

## Big-$\Theta$ Notation
$f(n)$ is $\Theta (g(n))$ if
$$f(n)=O (g(n)) \cap f(n)= \Omega (g(n))$$

A multiple of the function can bound it from above and below.

## Examle of Big-$\Theta$ notation
![[Pasted image 20210204174736.png]]
![[Pasted image 20210204180437.png]]

# Usage
- Big-O most common
- most misuses $O(f)$ instead of $\Theta (f)$ (a stronger statement)
- any $O(n^{2})$ is $O (n^{3})$
- $O(n^{2})$ could be slower than $O (n^{3})$
- $\Theta (n^{2})$ is always faster than $\Theta (n^{2})$

## Note
- for average case half the worst cases input?
