# Displacement addressing
![[Pasted image 20210125162149.png]]

Let's you jump through and quickly get memory which are a certain distance from one another.

## Features
- allows walking through arrays


## Four types:
- Relative
	- address = A + (PC) - program counter
- Base Register
	- address = A + (R) where R is special register
- Index
	- ??
- Scaled
	- address = offset + (R) + scale $*$ (R'), where R and R' are  registers in the address field
	- ![[Pasted image 20210125162633.png]]