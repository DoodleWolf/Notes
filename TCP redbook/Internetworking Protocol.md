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

### IP routing algorithm
![[Pasted image 20220724212325.png]]
- every host must have an IP routing algorithm that supports subnetting (same subnet mask unless specific in subnet)
- could use proxy-ARP if not supporting subnetting
![[Pasted image 20220724213008.png]]

### Methods of delivery
![[Pasted image 20220724213111.png]]
(connectionless protocol can do any; connetion only unicast)
- Broadcast: done by using all ones in the respective areas (network, host, subnet)
	- subnet must be careful that each router doesn't forward again therefor duplicating
- Multicasting: uses specific address for host groups
- Anycasting: connections are made to the first host in the group that responds

### Intranets: private ip addrs
Reserved address for non-internet aka private/internal use:
- 10.0.0.0: 1 Class A
- 172.16.0.0 - 172.31.0.0: 16 class B
- 192.168.0.0 through 192.168.255.0: 256 class C
These are advised to not be externaly advertised and discarded by external routers

### [[Acronyms#NAT|NAT]]
since only a small number of hosts in a private network need to speak to the internet, those host can get official IP addr
![[Pasted image 20220724215650.png]]
- updating the ip packet the checksum must also be adjusted (complicated for FTP)
- uses a pool of external addr to connect to internal addr 
- keeps track of what's been used before until idle past configured timeout limit
- must be configured to which internal hosts can use the NAT

### [[Acronyms#NAPT|NAPT]]
like NAT but also translate TCP/UDP
- maps private addr to one global uniq addr
- translation of source port for outbound and dest port for inbound in TCP/UDP header
- can handle [[Acronyms#ICMP|ICMP]] query type packets

#### Limitations
- NAT cannot handle application protocol IP addr stuff
- can't handle TCP/UDP fragments since only the first part has a header
- has problems with IPSec end-to-end authentication but IPSec can do what NAT does with VPNs(?)

### [[Acronyms#CIDR|CIDR]]
Orders not on the classs of network but on the high order bits (by IP prefix)
- each table entry has a 32bit IP addr and a 32-bit network mask < ip_addr net_mask >
- called supernetting
![[Pasted image 20220724231728.png]]
- ip addr represent physical topology not org topology
- network topology should follow continental/national boundaries
	- those  (rare few) that don't get transit routing domains

Network providers types:
1. no default inter-domain routing
2. default inter-domain but  req explicit routes for most ip addr
3. default inter-domain and have a few explicit routes
4. inter-domain with default routes

### IP datagram
![[Pasted image 20220725115304.png]]
- VERS: version (current 4, experimental 5, also 6)
- HLEN: header length in 32-bit quantities
- Service type: the QoS
	![[Pasted image 20220725120611.png]]
	Precedence
		• 000: Routine 
		• 001: Priority
		• 010: Immediate 
		• 011: Flash 
		• 100: Flash override 
		• 101: Critical 
		• 110: Internetwork control 
		• 111: Network control
	TOS
		• 1000: Minimize delay 
		• 0100: Maximize throughput 
		• 0010: Maximize reliability 
		• 0001: Minimize monetary cost 
		• 0000: Normal service
	MBZ: reserved for future use
- total length: total length of datag, h and data
- ID: number for fragmentation
- FLG: flags ofr fragmentation: 
	- 1st bit must be 0
	- 2nd: 0 can frag; 1 can't
	- 3rd: 0 if last frag; 1 there are more frags
- Fragment offset: to help recovery; contains the number of bit segment before
- TTL: supposed to be time to live but is really hops to live
- Protocol number: 
![[Pasted image 20220725122831.png]]
- checksums header (if mismatch discards)
- options: there are three diff types:
![[Pasted image 20220725124408.png]]
	- fc: whether the option is copied on fragmentation (1 yes; 0 no)
	- class:
		- 0 control
		- 1 reserved
		- 2 debug and measure
		- 3 reserved
	- option number:
		- 0: if ip header length doesn't mathc actual length {class = 0; fc =0 }
		- 1: no operation -> used to align {class=0; fc=1}
		- 2: security: us dep of def uses {class=0; fc=1}
		- 3: loose source routing: {class=0; fc=0}
		- 4: internet time stamp: {class=2; fc=0}
		- 7: record route: {class=0; fc=0}
		- 8: stream id: used with SATNET {class=0; fc=1}
		- 9: strict source routing: {class=0; fc=1}
	- length: of the whole option
	- option data: data to relevant option
- padding: to pad option

#### Fragmentation
Different hosts have [[Acronyms#MTU|MTU]] so the IP datagram must be broken down.
1. check whether fragmentation can happen with frag. flag
2. split based on [[Acronyms#MTU|MTU]]
3. options are checked if they need to be copied
4. new header length
5. new total length
6. checksum re-calculated
Note: netstat command can be used on some IP hosts to see how they fragment

#### Loose source routing
Loose because there is no strict route
![[Pasted image 20220725143820.png]]
- 131 decimal is the option type
- pointer: says which ip at currently
- route data: a series of ip-addrs

if pointer < length then:
1. take next ip addr and put in dest ip addr
2. put local ip at the source list where pointer is
3. increment pointer by 4
4.  send the datagram to the new ip addr

#### Strict source routing
Same as loose source routing, except the intermediate must be sent directly to the next ip addr.

#### Record route
Same as loose except insead route data is empty and filled in at each step.

#### Internet time stamp
can be used for debugging
![[Pasted image 20220725144857.png]]
- pointer points to next free time stamp
- oflw: number of devices unable to be registered due to lack of space in data field
- flag: 0 time stamps only; 1 time stamp + ip; 2 prespecified ip's which log their time
- timestamp: 32bit milisec since midnight GMT


## [[Acronyms#ICMP|ICMP]]
to inform of errors in datagram proccesing [[Acronyms#ICMP|ICMP]] is used
- ICMP is a higher-level protocol
- used to report errors
- sent for first fragment error not all of them
- not sent from broadcast or multicast dest addrs
- routers usually always generate errors, hosts might not
![[Pasted image 20220725145739.png]]
![[Pasted image 20220725145751.png]]
- 0 and 8: to check whether host is active (using ping)
- 3: self-explanitory
	![[Pasted image 20220725145948.png]]
	header contains one of the following:
![[Pasted image 20220725150051.png]]![[Pasted image 20220725150058.png]]
- 4: no buffer space; datagrams are too fast
- 5: should send to ip addr in the ICMP msg instead 