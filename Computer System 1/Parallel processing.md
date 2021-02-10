# Parallel processing
Multiple cores doing things at the same tiems

Single cores can do one thing at a time:
- time slice
- process swap

Definining a parallel workstream is a lot harder than it appears

## Amdahl's Law

### One core
the effort expended on acheiving high parallel procesing rates is wasted unless it is unaccompanied by achievements in sequential processing rates of very nearly the same magnitude

$T_{s}$ - total time required to execute task
$W_{s}$ - bits that must be done sequentialy
$W_{p}$ - bits that can be done parallel (but there is only one core)
$$T_{s}=W_{s}+W_{p}$$

### Multiple cores

$P$ - amount of cores (?)

$$T_{s}=W_{s}+\frac {W_{p}}{P}$$

### Value of parallization
Diminishing returns
![[Pasted image 20210130133044.png]]

## Flynn's Taxonomy
- SISD - single instruction, single data - conventional sequential machine - serial program
- SIMD - a single instruction, multiple data - single operation on multiple elements of data - "a vector machine"
- MIMD - multiple instructions, multiple data - seperate sequences of instructions, (each with it program counter) operate on seperate data
	- ![[Pasted image 20210130134209.png]]
- MISD - multiple instruction, single data - different bit of hardware doing the same calculations on the same data - "voting circuit" to decide what answer is correct
	- useful for saftey critical systems (nuclear reactor, spaceship)

## Symmetric multiprocessor - SMP
![[Pasted image 20210130134729.png]]
Multiple CPUs share main memory and I/O (most things aren't going to want to talk to main memory and I/O)
- scalable until bus is saturated
- MIMD system

### Cluster
to deal with bus saturation
![[Pasted image 20210130135238.png]]

Used by:
- Infiniband
- Myranet

#### Spectrum of granularity
[[Pasted image 20210130135729.png]]
- course-grained message-passing
	- typical one

![[Pasted image 20210130135909.png]]
- fine-grained message-passing
	- vey expensive
	- tiling it up with transporters 

## Process based message passing
![[Pasted image 20210130140214.png]]

process is self-contained

### Blocking send
- **Blocking send** A stops until the message is got to B
	- if B skips the message somehow (crash or hanging maybe) then A will indefinitely be waiting

- **Blocking receive** B waits until A sends a message
	- A skips sending the message (maybe from crashing) and B waits forever

### Non-blocking send
- A sends message to B and keeps going
	- in case message is not received A keeps them in a buffer (this buffer can overflow if many mesages are sent)
- B keeps going whether it receives the message or not (perhaps altering the function of the program)


## Thread based message passing
threads can see all data and all resources
- massive potential for data contention and collision
- program counter becomes multivalued
-  hard to debug


## Instruction level parallelism
![[Pasted image 20210130141454.png]]
through smartness you figure out how to only use one ALU instead of two (doing two things in parallel on the same ALU)
Transparent to the user
- compilet has to deal with it
- needs special hardware (eg AVX-512 )

### Example
![[Pasted image 20210130142005.png]]
![[Pasted image 20210130141952.png]]
now we try to squash the tree to minimize instruction amount
![[Pasted image 20210130142157.png]]
![[Pasted image 20210130142243.png]]
alternative 
![[Pasted image 20210130142344.png]]
![[Pasted image 20210130142359.png]]