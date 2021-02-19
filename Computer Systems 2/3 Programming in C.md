# Origin
- Created in 70's
- 24 KB of RAM
- for development of UNIX
- Outcome: minimalist, pragmatic, portable and close to hardware, core language has no I/O and no dynamic memory management
- Fortran -> algol 60 -> BCPL -> B -> C -> C++ -> Java

# When to use
- low-level hardware access is required
- runtime resources are critical
- realtime behaviour is critical (exactly what it'll do)
- short bits of code

conveniet way to write:
1. write everything in Python
2. Profile
3. replace hotspots with C


# Translation Units
- Scopes: program, file, function/block
- Programs are organised in files
- Files can be compiled independently

![[Pasted image 20210214150351.png]]

### header *.h
- contains declarations for exposed functions and variables
- included with preprocessor commands (that cut and paste in certain places)
- where the documentation is


# Things to be aware of
1. Unspecified behaviours (behaviour has to be specified in langue specification)
- size of int is not specified (adapts to hardware)
- allows for freedom for the compiler design
2. Undefined behaviours (don't know what will happen)
- error for which the standard does not prescribe any action
3. Unexpected behaviours (specified but not what the programmer wants)
4. In some contexts zero is special (any value not 0 is true, zero byte marks the end of a string, a pointer to the address 0 is invalid)
5. rules for type promotions and conversions
6. operator precedence (putting parenthesis indicates that you're overriding precedence)