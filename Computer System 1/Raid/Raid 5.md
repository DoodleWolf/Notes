# Raid 5
![[Pasted image 20210125185853.png]]
(the subscript p is where the parity would be)
## Features
- Like [[Raid 4]] but parity is spread between the drives.
- much less bottle neck since parity is on seperate disks and can be read seperately
- Problem: lots of disks can result in multiple disk failures which won't allow the parity to get it back

## Raid 6
- [[Raid 5]] but with double parity