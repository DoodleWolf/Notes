# IP
STD 5; a unrelaible, best-effort, connectionless packet delivery protocol
- 32-bit unsigned binary value
- [[Acronyms#DNS|DNS]] handles mapping between numbers and easier names "myhost.com"
- IP addr = < network number >< host number >
- used to uniquely identify a host on the internet
- each ip datagram has a destination and a source IP addr
- to send datagram the target ip addr must be translated to a physical addr (e.g. using ARP)
- [[Acronyms#RIR|RIR]] administer network numbers (regions have seperate orgs)

### Class-based IP addr
![[Pasted image 20220724160609.png]]
- A: 7bits for network and 24bits for host (for large # of hosts)
- B: 14bits for network and 16bits for host (for a small # of hosts)
- C:  21bits for network and 8bits for host (for medium # of hosts)
- D: reserved for multicasting
- E: for future experimental use

### Special IPs
- host number all bits 0 : this is the host
- network number all bits 0 : over this network
- host all bits 1: all hosts
- network all bits 1: all networks
- Class A network 127.0.0.0 : loopback : interfaces that process data within the local system
![[Pasted image 20220724161549.png]]

### Subnets
If a network has too many hosts instead of getting a new IP they create a subnet
- IP addr: < network number >< subnet number >< host number >
- local addr = subnet number and host number

#### Subnet masks
The division is done using a 32bit subnet mask:
- if bit in position n = 0 : in position n there is a host number
- if bit in position n = 1 : in position n there is a subnet number
- the first bits for network number are all 1 or 0 but are not used
- using non-contiguous subnet masks is discouraged
- usually stored in a config file but can be requested

#### Types of subnetting
- Static: all subnets in the same network use the same subnet mask
- Variable length: subnets can have varying subnet masks; an existsting subnet can be split into two parts by adding another bit to the subnet
Both can be used. Dedicated routers interconnecting the subnets can handle the complexities.

### IP routing
how routers interconnect different physical networks
- devices can be hosts and routers
	- such routers have partial routing info. only knows: hosts that are directly attached to the same network, hosts explicitly defined, hosts which have an ICMP redirect msg, defaults dest

#### Types of routing
- direct: destination host is on the same physical network
- indirect: not on the same physical network; must use multiple hops to get there; the addr of the first is only needed