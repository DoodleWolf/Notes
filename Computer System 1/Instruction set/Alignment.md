# Alignment
- Native objects have fixed sizes no matter how much of them you use up.
- User defined structure have an arbitrary size
- if object of size $s$ at address $A$ is aligned if $A mod s = 0$

## Why?
Misaligned memory access requires multiple memory accesses to process.