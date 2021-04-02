## 9.1 Algorithm (Sequential Search)
Check each element starting from the first element incrementing by one.
Time complexity:
- Best: $\Theta(1)$
- Average: $\Theta(\frac{n+1}{2})=\Theta(n)$
- Worst: $\Theta(n)$


Pseudocode:
![[Pasted image 20210305140803.png]]

## 9.2 Algorithm (Binary Search)
Steps:
1. Pick mid-point
2. See whether mid-point is bigger or smaller than the searched-for element
3. Do the same either to the group left or right of the mid-point
4. Continue until mid-point is the searched-for element

Time Complexity: $\Theta (n)$

Pseudocode:
![[Pasted image 20210305141814.png]]

## 9.3 Definition (stable)
A sorting algorithm is stable if it does not change the order of two identical elements

## 9.4 Definition (in-place)
Memory complexity of $O(1)$

## 9.5 Algorithm (insertion sort)
keeps a subsequence of elements on the left in sorted order

Properties:
- Time Complexity: $O(n^2)$
- It is in-place
- It is is stable (we only swap if one is strictly smaller)

When to use: for small arrays that are already somewhat sorted

Pseudocode:
![[Pasted image 20210305151249.png]]

## 9.6 Algorithm (selection sort)
search for the smallest element and put it in the front and repeat

Pseudocode:
![[Pasted image 20210305151926.png]]

Properties:
- Time complexity: $O(n^2)$
- in-place
- not stable (because it can get swapped for a min value)
- at most $n-1$ swaps

When to use: when swapping is expensive

## 9.7 Algorithm (bubble sort)
bubble up items through the array

Pseudocode:
- Time complexity: $O(n^2)$
- in-place
- stable

Reading: Chapter 2 in both books