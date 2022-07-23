## Ethernet and IEEE 802
![[Pasted image 20220720102648.png]]
Main difference: Ethernet type vs. IEEE 802 length
- Type is used for different protocol existing on the same wire
- Length can vary on different trasmissions speeds for IEEE (caps at 1500 at 10Mbps?)

Can coexist (using >1500 type numbers for Ethernet)

#### DSAP
destination service access point
#### SSAP
source service access point


### SNAP
extension of [[#SSAP]] and [[#DSAP]] happens when 170 in both fields
![[Pasted image 20220720114244.png]]

### RFC 894
Ethernet types:
- 2048 for IP datagrams
- 2054 for ARP datagrams 

### RFC 948
- Ethernet compatible: using IEEE but using type for length
- IEEE: using 6 in SSAP and DSAP

### RFC 1042
Standard for IP datagrams over IEEE 802

### RFC 2464
IPv6 can be used on Ethernet



## [[Acronyms#FDDI|FDDI]]
Defines standards for 100Mbps fiber optic.
- Became standard RFC 1390 STD 0036
- RFC 2467 extends to IPv6
- 32bit internet -> 48bit FDDI is done through ARP dynamic discovery procedure
![[Pasted image 20220720114535.png]]

## SLIP
Serieal line IP: simple packet framing protocol RFC1055, replaced by PPP
Defines a sequence of characters that frame IP packets on a serial line.

### PPP
Point-to-point protocol: STD 51 and elective. For different kinds of point-to-point (communication between two endpoints) links
Main components:
- encapsulates datagrams
- [[Acronyms#LCP|LCP]] (to establish , config and test data-link connections)
- [[Acronyms#NCP|NCP]] config and establish diff network-layer protocols

[[Acronyms#LCP|LCP]] phases
1. link establishment and negotiation
2. link quality determination
3. authentication (agreed to phase 1)