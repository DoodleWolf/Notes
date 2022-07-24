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

### PPP on SONET and SDH 
Sync Optical Network and Sync Digital Hierarchy links: octect-sync multiplex scheme for single/multi fiber and CATV coaxial cable
- starting transmission rates at 155.52Mps
- By integer variations of transmission rates (51.840Mbps)
![[Pasted image 20220724111051.png]]
 - has path signal label; hex CF for PPP; multiframe is unused and 0

### Multi-Path Channel+
allows multiple rand write subchannels to work as a single transmission group
- MPC+ refers to [[Acronyms#HPDT|HPDT]]
- uses each subchannel is half-duplex
- MPC+ activates whenever a read and write subchannel is alive

### [[Acronyms#ATM|ATM]]
- two important LAN interfaces for ATM: Classic IP and LAN emulation
-  ATMARP and InATMARP for address resolution RFC 826,  2390, 2225
- ATMARP as ARP but with unicast server ATM support: IP addr
- InATMARP same as InARP: hardware addr
- addr resolution in a PVC is InATMARP
- addr resolution in a SVC is ATMARP -> after the req an InATMARP req is sent and the client sends a response w/ the IP addr, ATM addr, Time stamp, Assoc VC
- ARP table add algorithm:
	- new ip addr: added to table
	- ip addr already exists but diff info: no modification
	- ip exists and same info: updates timeout info
	- if new ip addr over ARP_REQUEST: added to table
- table entries are valid for 15min max client side and 20min min server side

### Classic IP over ATM
- Cell layer: all info on 48 data byte with 5byte header called cells
- Route layer: cell header has the path to take on the network
- VC: can be either PVC or dynamic SVC
- end-user: PDUs specify AAL type (there are 4 which offer diff services); the type is known by the VC endpoints 
	- AAL5 is like LAN MAC
- addressing: 20byte OSI NSAP-based addr or E164 public UNI adress
- broadcast: no broadcast like LAN but exists multicast function

#### Logical IP Subnetwork
A closed subnetwork in an ATM network where each host can speak directly to one another and uses an IP router to talk to other LIS on the network. The router is also a part of the ATM

#### Multiprotocol encapsulation
- can uses different VCs for diff protocols
- can use LLC

#### AAL5 CPCS-PDU
![[Pasted image 20220724135745.png]]
- payload
 ![[Pasted image 20220724140833.png]]
	 - datagram with ip header
	 - LLC to show if SNAP
	 - OUI - organizationally unique identifier
	 - PID  - protocol identifier
- Pad to fit ATM cell
- CPCS-UU - user-to-user identification to transparently transfer uu info
- CPI - common part indicator to align the PDU with 64bits
- Length - indicates length, max value 64KB - 1
- CRC - protects everything but itself

MTU: 9180bytes; header is 8bytes so PDU is 9188bytes


### ATM LAN emulation
Still in the works according to the red book but supposed to make the system think it's a part of an actual LAN. 

I'm skipping this.

### Multiprotocol over ATM
Basically multiple layers that have a LAN router, I think?


