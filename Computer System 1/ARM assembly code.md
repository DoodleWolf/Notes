All ARM run on the same instruction set
- 32-bit instruction set
- has an alternative thumb instruction set (useful for small ARM systems)
- (can mix between them)

## ARM Registers
- 16 32-bit registers R0-R15
- 3 are special
![[Pasted image 20210130173503.png]]
![[Pasted image 20210130173744.png]]
Status register tells you if the conditional was true or not

## Code example
![[Pasted image 20210130173612.png]]

sub for normal condition
subs :
![[Pasted image 20210130173938.png]]

### if else
![[Pasted image 20210130174123.png]]

### Memory access
![[Pasted image 20210130174340.png]]
![[Pasted image 20210130174544.png]]

### loop
![[Pasted image 20210130174613.png]]

### conditions
![[Pasted image 20210130174755.png]]

### stack
- an area in memory we can use when running out of registers
- CPU can tell current stack positiong through stack pointer
	- R13 (called sp in assembler)

### Return addres RA
![[Pasted image 20210130175323.png]]
^ not actual code
- achieved by storing PC 
- then the to return from the branch put it back to the PC

ARM stores the Return Adress in R14
![[Pasted image 20210130175512.png]]
![[Pasted image 20210130175527.png]]

#### example of LR
![[Pasted image 20210130175621.png]]
BX can tell which instruction set it's jumping through

### compile on Pi
![[Pasted image 20210130175740.png]]

ever wanna check how compiler handles c code?
![[Pasted image 20210130175834.png]]

## r0 is the shell value
![[Pasted image 20210130180034.png]]
![[Pasted image 20210130180054.png]]
![[Pasted image 20210130180040.png]]

## to load big numbers
![[Pasted image 20210130181205.png]]

## printing
![[Pasted image 20210130181604.png]]
^ tells system what the formay of what we're doing looks like
![[Pasted image 20210130181615.png]]