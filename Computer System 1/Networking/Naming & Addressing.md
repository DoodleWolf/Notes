# Name & Addressing (between different layers)


![[Pasted image 20210124143631.png]]

## DNS - Domain name service

A way to map domain names to an IPv4 or IPv6 address. It operates at the [[Application Layer]] 

### Types of record:
![[Pasted image 20210124143853.png]]


### How it works:
1. Computer queries home router
2. router queries cache
3. if not there router queries DNS server
4. and so on until local server

## ARP / NDP - address resolution protocol (v4) / neighbour discovery protocol (v6)

Translates IP addresses to MAC addresses