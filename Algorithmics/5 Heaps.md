### 5.1 Definition (min- heap)
A binary tree with:
1. every level above the lowest full (and the nodes on the lowest are to the left)
2. each child is greater than or equal to parent
![[Pasted image 20210224221127.png]]

Insertion:
1. add the element to the next available place
2. move the node up the tree (by swapping with it's parent) until the ordering is fine (ie it's parent is smaller than or equal)


### 5.2 Definition (priority queue)
A queue with weighted elements:
1. the head of the queue is the high priority element (smallest number)

![[Pasted image 20210224222135.png]]


### 5.3 Method (removeMin)
1. pop root
2. put the last element in the root (replace)
3. swap down the replaced root with the min child until ordering is good

### 5.4 Implementation (heap)
An array can be used for effective implementation of the heap
![[Pasted image 20210224224139.png]]


### 5.5 Code (Heap/Priority Queue)

![[Pasted image 20210224224648.png]]

Adding an Element
![[Pasted image 20210224224820.png]]

"pop" or removemin()
![[Pasted image 20210224230608.png]]

### 5.6 Time Complexity (Heap)
![[Pasted image 20210224231101.png]]

### 5.7 Code (fake Heap sort)
![[Pasted image 20210224231713.png]]

$\Theta (n \log (n))$
- add $n$ elements, remove $n$ elements
- each add/remove is $\Theta (\log (n))$


### 5.8 Algorithm (Standard Heap Sort)
1. Start with non-sorted array
2. transform into max-heap without additional storage
3. repeatedly remove the max from the current heap

### 5.9 Code (Standard Heap Sort)
![[Pasted image 20210224232258.png]]
(percolate is given the list size)