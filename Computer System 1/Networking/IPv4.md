# IPv4
## Internet Protocol version 4

Addressing standard used in [[Internet Layer]]
First standardized in 1982.

### Features:
- Each node has a unique 32-bit IP address
- Written in octet-grouped dotted-decimal  notation
	- a.b.c.d each can only go up to 274
- Header (of variable length):
	- ![[Pasted image 20210124140204.png]]
	-  version field indicates ipv4
	-  dscp used for traffic managment
	-  brown layer: used for fragmentation (if your packet is to big it's broke down)
	-  TTL: how many hops it can go

## IPv4 Exhaustion
Has space for about 4.3 billion addresses (not enough for every person let alone their devices)

![[Pasted image 20210124140613.png]]

### Two solutions:
- Network Address Translation
- IPv6

