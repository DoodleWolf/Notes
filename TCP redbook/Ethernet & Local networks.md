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

#### [[Acronyms#LCP|LCP]] phases
1. link establishment and negotiation
2. link quality determination
3. authentication (what was agreed to in phase 1)
4. [[Acronyms#NCP|NCP]] is configured
5. link can be terminated whenever

![[Pasted image 20220723160756.png]]
- Protocol: datagrams in info (specified in RFC 3232)
- Info field: datagram
- Padding: padded up to [[Acronyms#MRU|MRU]] -> default 1500 octets

#### IPCP
[[Acronyms#NCP|NCP]] for IP which works the same as [[#Acronyms LCP LCP phases|LCP]] 
Important note: Van Jacobson Header Compression is used

### [[Acronyms#ISDN|ISDN]]
How to use PPP over ISDN pp links
- Basic Rate Interface (BRI) 2 64Kbps B-channels for data, 16Kbps D-channel for control info
- Primary Rate Interface (PRI) up-to 30 B-channels and one 64kbps D-channel
- data term equip handles encoding
- full-duplex (data goes both ways at once)
- same framing method
- [[#Acronyms LCP LCP phases|LCP]] applies
- [[Acronyms#MRU|MRU]] 1500 or 2048 bytes
- [[Acronyms#MTU|MTU]] usually caps at 1500 unless specified


### X.25
Packet-switching protocol for wide area networks (WAN: large comp. netw. over large distances).
- Allows for multi-protocol multiplex circuits
- PDUs (protocol data units) are sent on the packet boundary which specify the network protocol used and the data
	- M bit for fragmentation
	- first octet for CUD (call user data) to specify network ISO/IEC TR 9577
		- hex CC for IP
		- hex 81 for CLNP
		- hex 82 for ES-IS
		- hex 80 for IEEE SNAP
		- hex 00 for multiplex multiple networks (following packet sequences must all have hex values identifying their network)
		- hex C5 for blacker x.25
		- hex CD for ISO-IP
- every system must support CC
- good for systems with limited virtual circuts but must use multiplexing

### Frame relay
virtual circuits for connections between stations on same frame relay network
- use cases: between LANs and WAN endpoints
- packets use Q.922 Annex A frame 
![[Pasted image 20220723181022.png]]
- Pad is all zeroes
- NLPID uses ISO/IEC TR 9577 (just as X.25) but 0x00 as inactive set
- no common max or min frame; must be configurable
- bridged / routed packets are indicated in NLPID
- [[Acronyms#XID|XID]] allows negotiating: max size, retransmission timer and max outstanding info (I) frames (if not exchanged must be set by agreement of DLC endpoints)
- protocol addr resolved with [[Acronyms#ARP|ARP]] in SNAP
- to move IP addr to a DLCI stations send IP addr and DLCI by unsolicited ARP by setting source and dest IP as the same on that DLC