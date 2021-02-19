# Embedded Computing
![[Pasted image 20210205180255.png]]

## Microcontroller
- low power requirement (a few mA)
- Flash memory: 2-138kB
- RAM: 0-32 kB
- Easy to program in C or C++ (rarely assembly, mid 80s was assembly)
- Cross-compiler setup relatively simple
- In-system-programmers are cheap
- In quantity they can be very cheap ($12 for raspberry 0?)
- very low sleep power (and fast wake) => sleeps between instruction set


## System on Chip
- typically ARM core cpus 
- Flash and RAM in MB range
- Cross-compiler setup is complex 
- (easier mbed cloud based)
- micro python gap between low-level C and embedded computer

## Embedded Computer
- convenient development with login console
- sufficient fo image processing
- 100mA 
- System boot takes time (sleep not efficient)
- complex interrupt architecture makes precise timing of IO difficult (use microcontroller for better control)

## LaFortuna
![[Pasted image 20210205182343.png]]
![[Pasted image 20210205183646.png]]

### AVR Micro controller
![[Pasted image 20210205184621.png]]
- very popular series of microcontroller
- complete computer on a single chip