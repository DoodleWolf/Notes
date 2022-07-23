## 12.1 Definition (Matching)
A set of edges without common vertices (an independent edge set)

## 12.2 Definition (Covered (set of vertices))
A set of vertices is covered by a matching if all vertices are in the matching
(vertices that aren't in the matching are called **free/unmatched**)

## 12.3 Definition (maximal matching)
A matching $M$ is maximal if it is not a subset of any other matching (i.e., no more edges can be added to it)

## 12.4 Definition (maximum matching)
A matching $M$ that contains the largest possible number of edges

## 12.5 Remark
$M$ is a maximum => $M$ is a maximal (but not necesarilly the other way around)

## 12.6 Definition (Augmenting Path)
A path $P$ is an augmenting path for a matching $M$ if the two end points of $P$ are un matched and the edges of $P$ alternate between being in and out of the matching

![[Pasted image 20210419164437.png]]

## 12.7 Theorem (Berge's Theorem)
A matching $M$ is maximum $\Leftrightarrow$ $M$ has no augmenting path

Enables us to turn any maximal matching algorithm into a maximum matching algorithm 

## 12.8 Algorithm (Bipartite Matching)
1. $M \leftarrow \emptyset$
2. Start DFS (depth-first search) at an unmatched vertex
3. While $\exists$ an augmenting path $P$ in $M$
	1. Flip the edges of $P$
4. Return $M$

(works because only odd cycles result a path with two adjacent unmatched edges)

- $O(|V||E|)$

## 12.9 Algorithm (Hopcroft-Karp Algorithm)
Improved Bipartite Matching algorithm by running BFS on the unmatched nodes to find other nodes then running DFS to find the augmented path

##  12.10 Roadmap for Maximum Matching Algorithms
![[Pasted image 20210419195559.png]]

## 12.11 Definition (blossom)
A blossom is an odd-cycle where a path (stem) of even length with an alternating matching edges exists.

![[Pasted image 20210419201450.png]]

 ## 12.12 Algorithm (General Maximum Matching / Edward's Blossom)