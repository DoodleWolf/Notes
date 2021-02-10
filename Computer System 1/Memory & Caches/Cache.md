# Cache
Since CPU needs data faster than DRAM can provide there is a sort of buffer between DRAM and CPU with SRAM which stores recently used things and pulls stuff from main memory.
![[Pasted image 20210125171230.png]]

## Operation overview
1. CPU sends an address to cache
2. cache sees if it knows the content
	- if known - cache hit, if not - cache miss
3. if not found, has to go fetch it from RAM
4. RAM gives it a ton of cache lines (more data than we need)
	- allows to speed up algorithm to think of as cache lines
	- gets stuff close by quickly

## Cache design parameters
- mapping function (deciding which cache lines to pull?)
- replacement algorithm (how to decide which lines to invalidate and replace)
	- tends to share blocks and invalidate them

## Cache miss-rate
![[Pasted image 20210125172511.png]]

## In-reality three level cache
- L3 to shield from DRAM directly
- L2 shield from other cores
- L1 direct cache
![[Pasted image 20210125172757.png]]

## Direct Mapping (simplest method)
![[Pasted image 20210125173052.png]]
- Blocks of RAM share same cache entry
- gets bad when going to higher levels of RAM


## Direct Mapping Cache organization
![[Pasted image 20210125173313.png]]
 _not super sure how this works exactly_
- tag indicates which part of RAM it is
- word will tell you even or odd (??)
- then it can be compared with the line to see if it's what you want

## Fully associateive cache organization
![[Pasted image 20210125173631.png]]
Uses a large tag and lots of comparison to tell you whether it has the word you're looking for. Can be slower since it has to compare lots.