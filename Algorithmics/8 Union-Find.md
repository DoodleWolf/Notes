## 8.1 Definition (dynamic connectivity)
A relationship/command-set between a set of $N$ object (dynamic => can change)
Commands:
- **union**: connects two objects
- **isConnected**: check if two objects are connected (via path)

## 8.2 Definition (Union-Find/Disjoint set)
Data structure (used for pattern recognition?)
Commands:
- **Find**: checks which equivalence class a given object belongs to
- **Union**: merge two given equivalence classes into one


Data-structure that maintains disjoint sets.  A representative, a member of the set, is used to represent the whole set.

Operations:
- **MAKE-SET(x)**: make a set with just $x$
- **UNION(x,y)**: unite the sets that containt $x$ and $y$ (and destroy those sets afterwards)
- **FIND-SET(x)**: returns representative of set with $x$

## 8.3 Implementation (Quick-Find)
Create an array ($id[]$) where the position represents the element. Upon connection equate the elements in the array.
**Find**: return id from id array
**Union**: change id of all to match the latest id
![[Pasted image 20210305112702.png]]

Time Complexity:
- Initialisation: $O(n)$
- find: $O(1)$
-union: $O(n)$

## 8.4 Code (Quick-Find)
![[Pasted image 20210305112907.png]]

## 8.5  Implementation (Quick-Union)
The id array stores the parent of the element and the tree represents the union
**Find**: go up the tree till you reach root (id position = id)
**Union**: make root direct child
![[Pasted image 20210305113515.png]]

Time Complexity:
- init: $O(n)$
- find: $O(n)$
- union $O(n)$


## 8.6 Code (Quick-Union)
![[Pasted image 20210305114242.png]]

## 8.7 Implementation (Quicker-Union/Kruskal's Algorithm)
Take advantage of path compression and weighted graphs
- **path compression**: when find is used bring all elements in the path to the root
- **weighted graph**: keep track of each graph's size and when combining make the larger graph becomes the smaller graphs direct child

Time Complexity:
- init: $O(n)$
- find: $O(\log^*(n))$ (Hopocroft & Ullman, 1973)
- union: $O(\log^*(n))$

where
![[Pasted image 20210305130644.png]]


Reading: 
- Chapter 1 in Sedgewick & Wayne **Algorithms**
- Chapter 21 in Cormen **Introfuction to Algorithms**
