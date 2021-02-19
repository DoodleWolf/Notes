# Source to Memory
## Why
- Important for understanding C
- useful for understandign error messages

## Compilation
![[Pasted image 20210205155958.png]]
Compilation:
Source code -> compiler -> executable

Cross-compilation
source -> compiler (host) -> executable (target) 

Used when compilation on target is impractical (e.g. low capability, first compiler on new hardware)

Architectures may vary for host and target:
- memory (von Neumann/Harvard)
- word size
- endedness


## Build Process
![[Pasted image 20210205160319.png]]
- Compiler assigns program and data to sections (thinks about account scope and const)
- Linker assigns sections to virtual memory (so that OS can have flexibility for where the memory go)
- Loader assigns sections to physical memory 

### Errors and Options
- Interpreting error messages
- considering configurations options
	- compiler optimization (change code output real time)
	- compiler warnings (e.g. returning value because of OS but there is no OS on embedded system hence no need)
	- selection of libraries (e.g. why have floating point libraries if you're not using them)


### Intermediate Files
![[Pasted image 20210205161055.png]]
- .o makes sure the bites are specific architecture
- .elf binary format 
- .hex the bites that go into memory


Relocateable (.o) - no fixed address assigned
Execuatable (a.out / exe) - fix the infrastructure (?)
Shared object (.so/dll) - share between different executables (so that it needs not get compiled for each source code)
ELF -> executable and linakable format

### ELF
![[Pasted image 20210205161831.png]]
![[Pasted image 20210205162512.png]]
- .data goes to Flash at the start but goes to RAM when run
- .rodata has constants
- .data initialize global/static variables (set to 0)
- .bss unitialized global variables (set to 0)
(you don't intialize local variable in C)

#### intialize
- to not have set register to value (for local)
- innit global because C does not know what you plan to do with it

### Translation Units
C-Source 3 scopes:
1. program wide scope
2. file scope
3. block scope (C89: only function scope)

Programs are organized in files
files compiled independently (.c -> .o)
