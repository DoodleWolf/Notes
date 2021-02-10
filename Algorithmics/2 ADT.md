

# Stack
## Definition
Can only remove the last element added 
(Last in First Out memory - LIFO)

### Standard operations
- push(item) will add the item to the top of the stack
- peek() looks at the top element
- pop() returns and the removes the element
- isEmpty()

## implementation 
can be implemented using an array or linked list

### sudo code implementation through arrays
![[Pasted image 20210209120904.png]]

### Complexity of Stack
All $\Theta (1)$

## Application
- Reversing array
- Parsing expression for compilers (parentheses, XML tags, arithmetic expression) - push when seeing open paran. and pop when you see a closed paran pop, if ends empty => all good
- Clustering algorithm

### Example of evaluating arithemtic expression
![[Pasted image 20210209122239.png]]

### Java Stack (bad way to do stacks)
Java has a Stack class with push, pop, peek, empry and search (search should not be)
+ extends vector class (a stack isn't a vector!)
=> stack should not be a class but an interface

# Queues
## Definition
FIrst-in-first-out memory model

### Standard operations
- enqueue(elem) - add elem
- peek() - look at the oldest element
- dequeue() - remove oldest element
- isEmpty()

## Application
- In OS systems : print queues, job queues
- Communication / message passing

# Priority Queues
## Definition
Next element to get is the one with the highest priority

### Standard operations
- insert (elem, priority)
- findMin() - find highest priority
- deleteMin()

## Application
- OS task completion
- Greedy algorithms (Prim's min spanning tree algorithms)

## Implementation
Can be implemented with linked list, binary or heap (binary tree implemented with array ->best)

# List
## Definition
A list is a collection where the order of elements is important
### Standard Operations
- add(elem, pos) -> pushes the rest
- remove(pos)
- set(elem, pos) -> changes the element at position
- get(pos)
(pos - position, elem - element)

# Sets
## Definition
no ordering or repitions
### Standard operations
- add(elem)
- remove(elem)
- contains(elem)
- size()
- isEmpty()

# Maps
## Definition
Unordered data type with each looking like key:data
(no duplicate keys -> dupes are in multimaps)

# Clustering
## Problem
Find clusters of connected cells

Assume Graph interface with getNeighbours(Node n) and isOccupied (Node n)

## Clustering algorithm
cluster nodes: use set for as order does not matter
uncheckedNodes: use stack as we just have to check them one by one
![[Pasted image 20210209124804.png]]


# Array
- doulbe the size everytime the capcity is reached
- adding is $\Theta(1)$

# Non-continguous 
## Linked  list
- Has head for intial reference
- every element has element then pointer to next element
- adding an element will move the header pointer

### operations
- get_head()
- get(i) $\Theta (n)$
- remove(i) $\Theta (n)$
- remove_head()

### Java implementation
- double linked list

## Skip list
- linked list which supports binary search

![[Pasted image 20210210134406.png]]
![[Pasted image 20210210134508.png]]