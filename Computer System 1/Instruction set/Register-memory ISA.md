# Register-memory ISA
![[Pasted image 20210124191855.png]]
One input - memory
one input - register
result > register

### Example: X=A+B
![[Pasted image 20210124191848.png]]
1.  Load A into register 3
2.  Load B and add register 3 into register 1
3.  store register 1 into X

## Advantages
- Data can be accessed directly from memory (slow)
	- but no extra load (fast)
- simple code generationa


## Disadvantages
- clocks per operand depend on where it is
- 