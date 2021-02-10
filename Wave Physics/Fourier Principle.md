# Fourier Principle
Represent a wave form in terms of different frequencies.

### Square wave
![[Pasted image 20210126232704.png]]

Spectrum: amplitude vs frequency graphs
![[Pasted image 20210126232801.png]]

## Fourier Synthesis
Generating a function can be generated by adding $\sin$ and $\cos$ functions (we will usually use time for /our variable)
![[Pasted image 20210126232917.png]]
- $a_{n},b_{n}$ coefficients
- could be finite amount of waves -> $\sum$

take the spectrum -> through it into cos and sin functions to get out function

(analysis is doing the reverse)

### Ingredients:
- Linearity ( a solution can be made of a sum of component solutions)
	- ### $\phi(x)=a \psi _{1} (x) + b \psi_{2} (x)$
![[Pasted image 20210126233233.png]]
	- we want to know that even if they're individual solutions their sum will be as well
- Orthogonality
	- ### $\lim_{\delta x \rightarrow + \infty} \frac{1}{\delta x} \int \limits_{x_{0}}^{x_{0}+ \delta x} \psi _{i}^{*} \psi_{j} \ \mathbf{dx} = 0, \ i \neq j$ 
		- where $^{*}$ is the complex conjugate
		- If $k_{i}=k_{j}$ for the function $\sin{k_{j}x}$ we get $\frac{1}{2}$ from the orthogonality test, this allows us to work out the coeff.
- Completeness
	- any function $\psi (x)$ may be written as a superpostion
	- ![[Pasted image 20210128141407.png]]

### Common basis functions:
(this could be pretty cool to research)
![[Pasted image 20210126234836.png]]
- they form a complete orthogonal set

## Uses
- Find frequencies \ wavenumbers present
- helps in enery \ power calculations
- propogation in dispersive systems
- Fraunhofer diffraction (??)
- Bandwith theorem \ Heisenburg uncertainty
- Convolution theorem

## Fourier Analysis
### Finding the amplitude of a component

^1366b8

$$ \psi (t) = \sum \limits_{n} a_{n} \cos{\omega _{n} t} + b_{n} \sin{\omega _{n} t}$$
$$ \text{multiply by }\cos{\omega_{k} t}$$
$$  \begin{align} \cos{(\omega_{k} t)}  \psi (t) & = \sum \limits_{n} [ a_{n} \cos{(\omega_{k} t)} \cos{(\omega _{n} t)} + b_{n} \cos{(\omega_{n} t)} \sin{(\omega _{n} t)]}\\
& = \sum \limits_{n} [ \frac{a_{n}}{2} ( \cos{(\omega_{k} t + \omega_{n} t)} +\cos{(\omega _{k} t - \omega_{k}t)} ) + \frac{b_{n}}{2}( \sin{(\omega_{n} t + \omega_{k}t)} + \sin{(\omega _{n} t - \omega_{k}t)]}
\end{align}$$ 
Now we take this wierd integral:
$$\begin{aligned} \frac{1}{\delta t} \int \limits_{t_{0}}^{t_{0} + \delta t} \cos{(\omega_{k} t)} \psi (t) = & \sum \limits_{n}\frac{a_{n}}{2 \delta t} \left( \frac{ \sin{(\omega_{k} t + \omega_{n} t)}}{(\omega_{k} + \omega_{n})} + \frac{ \sin{(\omega_{k} t - \omega_{n} t)}}{(\omega_{k} - \omega_{n})} \right) \\
& + \sum \limits_{n}\frac{b_{n}}{2 \delta t} \left( \frac{- \cos{(\omega_{k} t + \omega_{n} t)}}{(\omega_{k} + \omega_{n})} + \frac{- \cos{(\omega_{k} t - \omega_{n} t)}}{(\omega_{k} - \omega_{n})} \right) \\
& + \int \limits_{t_{0}}^{t_{0}+\delta t} \frac{a_{m}}{\delta t} (\cos{2 \omega_{m} t} + 1) + \frac{b_{m}}{\delta t}(\sin{2 \omega_{m} t} + 0) \end{aligned}
$$
Hence,
$$a_{m}=\lim_{\delta t \rightarrow \ + \infty}\ \frac{2}{\delta t} \int \limits_{t_{0}}^{t_{0} + \delta t} \cos{(\omega_{k} t)} \psi (t) \mathbf{dt}$$

### Solving square waves
- symmetrical about $t=0$ therefore we can look at just cosine terms $\Rightarrow \ b_{n}=0$
- we only need to consider the first period since it's periodic (introduce variable $T$ for the square waves period)
$$\psi (t) = \sum _{n}^{\infty} a_{n} \cos{(\frac{2 \pi n}{T} t)}$$

the integral is put within a period as that would be the same as integrating over all of time and dividing it (... umm sure)
$$ \begin{align} \int \limits_{-T/2}^{T/2} \cos{( \frac{2 \pi m}{T} t)} \psi (t) \mathbf{dt} & = \int \limits _{-T/2}^{T/2} \sum \limits_{n}^{\infty} a_{n} \cos{( \frac{2 \pi m}{T} t)} \cos{(\frac{2 \pi n}{T} t)} \mathbf{dt} \\
& = \int \limits _{-T/2}^{T/2} \frac12 \sum \limits_{n}^{\infty} a_{n}[ \cos{( \frac{2 \pi (m+n)} {T} t} + \cos{( \frac{2 \pi (m-n)} {T} t)} ] \mathbf{dt} \end{align}$$
in order to get rid of the other pesky terms we must remember that we are taking the integral over a full period hence and we now that $\int \limits_{0}^{\text{period}} \text{trig function}=0 \Rightarrow$
$$= \int \limits_{-T/2}^{T/2} \frac{a_{n}}2 \cos{(\frac{2 \pi (m-m)}{T}t)} \mathbf{dt}=a_{n}\frac{T}{2}$$

we know the factor for normalization, from [[#^1366b8 | finding the amplitude of a component]] we get
$$a_{m}=\frac2T \int \limits_{-T/2}^{T/2} \cos{(\frac{2 \pi m}{T} t)} \psi (t) \mathbf{dt} $$
to solve for $a_{n}$ we plug in $\psi (t)$ which we know for certain periods. 
![[Pasted image 20210127202031.png]]
$$ \begin{align} a_{n} & =\frac 2T \left( \int \limits_{-T/2} ^{-T/4} -a \cos{(\frac {2 \pi n \ } {T}t)}\mathbf{dt}+ \int \limits_{-T/4}^{T/4} a \cos{(\frac {2 \pi n \ } {T}t)}\mathbf{dt}  + \int \limits_{T/4}^{T/2}-a \cos{(\frac {2 \pi n \ } {T}t)}\mathbf{dt} \right)\\
& = \frac 2T \left( 2 \int \limits_{-T/2} ^{-T/4} -a \cos{(\frac {2 \pi n \ } {T}t)}\mathbf{dt}+ \int \limits_{-T/4}^{T/4} a \cos{(\frac {2 \pi n \ } {T}t)}\mathbf{dt}  + \right)\\
& = \frac{a}{ \pi n \ } \left( -2\sin{(\frac{2 \pi n \ }{T} \frac{-T}{4})}+2 \sin{(\frac{2 \pi n \ }{T} \frac{T}{4})} \right) \\
& = \frac{4a } {\pi n \ }\sin{ (\frac{ \pi n \ }{2}) }\end{align}
$$

Then plug in values for $m={1,2,..}$

## Simple explanation
1. write $\psi (x)$ as a sum of $\cos$ and $\sin$
2. find coeff. by orthogonality
	1. multiply by $cos$ or $sin$
	2. then integrate over some $t$ and "normalize" (ie solve without plugging in $\psi (x)$ and see what the factor on your coeff. is)
	3. then plug $\psi (x)$ to solve for coeff.

Confusion arises from different variations but they all essentially have the same idea.


## Analysis into othro-normal functions
### Orthno-normality
![[Pasted image 20210128141631.png]]

### Use it to find coefficient
![[Pasted image 20210128141651.png]]

### Normality of sinusoidal functions
$$F_{i}(t) = \alpha \sin{\omega _{i}} t \text{ where } \omega _{i}= \frac{2 \pi}{T} i \text{ and T is period}$$
now we normalize over an interval for the period 
$$\begin{align} \int \limits_{-T/2}^{T/2} F_{i}^{*}(t)F_{i}(t) \mathbf{dt} & = \alpha _{i}^{*} \alpha_{i} \int _{-T/2}^{T/2} \sin^{2} {(\omega_{i}t)} \mathbf{dt} \\
& = \alpha _{i}^{*} \alpha_{i} \frac 12 \int _{-T/2}^{T/2} [1-\cos{(2 \omega_{i} t)}] \mathbf{dt} \\
& = \alpha _{i}^{*} \alpha_{i} \left( \frac T2 - \frac {1}{\omega_{i}} \right)  \sin{2 \pi i}) \text{  i here is for the function number not complex} \\
& = \alpha _{i}^{*} \alpha_{i} \frac T2 \\
 \Rightarrow F_{i}= \sqrt{ \frac 2T} \sin{\omega _{i} t}

\end{align} $$

### Orthogonality of sinusoidal functions
![[Pasted image 20210128144945.png]]

### Finding the coefficients
![[Pasted image 20210128152235.png]]
- to uses this your function must be periodic
- i think this also implies symmetry on t=


### Complex Fourier Analysis
The aim here is to get pull together $a_{n}$ and $b_{n}$ into one component, in this case $g_{n}$
![[Pasted image 20210128153558.png]]

#### Solving for $g_{i}$
![[Pasted image 20210128154519.png]] side note: not colored $i$ is the complex number

since those will be integer multiples of the period they should cancel out except for in the case $i=j$
![[Pasted image 20210128154557.png]]

#### Alternative approach

^9f72bf

take the real value of a complex wave function
![[Pasted image 20210128155419.png]]

but this way we get an extra factor of 2:
![[Pasted image 20210128155501.png]]
((this happens because when we take the real part we add the conjugate and divide by half, getting rid of that factor))
((the factor isn't a bad thing, just have to stay consistent with what you're using))

### Continuous spectra
For period $T$,
![[Pasted image 20210128161354.png]]
If we change T, our spectra envelope stays the same but the difference between the frequencies $\omega$ decreases. (the graph is frequency vs amplitude)
![[Pasted image 20210128162111.png]]
With this idea in hand, we try to solve for the continuous spectra,
![[Pasted image 20210128162257.png]]

where we define $a(\omega)=\frac{a_{i}}{2 \Delta \omega}$ and can plug our previous results for $a_{i}$
![[Pasted image 20210128162454.png]]
- at the end $\Delta \omega= \frac{2 \pi}{T}$ is plugged in

#### if we use complex 
![[Pasted image 20210128162813.png]]

## Summary
![[Pasted image 20210128163114.png]]
![[Pasted image 20210128163240.png]]
![[Pasted image 20210128163253.png]]