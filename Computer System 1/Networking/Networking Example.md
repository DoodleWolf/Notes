# Networking Example

## I want to go to website https://abc.com
1. Computer sends a DNS request to find IP address
2. IP address gotten from router cache
3.  Our transport will be TCP since it's https
4.  Pick a random source port when creating socket
5.  Sets destination for known port of this protocol
6.  Use destination IP address 
7.  Send it to our gateway ?? because it's not a local address
8.  Look at the mac address of our gateway
9.  Gateway recieves packet
10.  Passes packet to [[Internet Layer]]
11.  Rewrites parts of the headers
12.  Sends it to the router
13.  Router finds interface for the address
14.  Destination recieves a link layer
15.  Confirms it is for them
16.  Passes it for the Transport layer which we got the port number for
17.  Passes it up to the application (web server)
18.  Then all the way back