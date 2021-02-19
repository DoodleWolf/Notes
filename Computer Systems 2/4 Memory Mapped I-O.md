## $\mu$C

microcontroller = CPU + Memory + Hardware Modules
![[Pasted image 20210214152508.png]]

## Control registers
Defintion: sets of flip flops whose inputs or outputs are wired into other circuits

CPU interaction:
- I/O instructions (I/O commands control I/O port registers)
**cons**:instruction set bits are precious; **pros**:convenient
- memory mapped I/0 (i/o registers have addresses reserved in memory)
**cons**: cache complications; **pros**:address space is very available

Use extended registers and normal registers for I/O so that you can use smaller addresses