## 6.1 Definition (B-Trees)
**Informally** 
B-Trees are balanced trees designed to keep related data close to minimize retrieval time. Used in databases (for large data).
-> $O(1) \neq$ taking from disk

**Formally**
- data is stored at the leaves
- $M$ is the order (maximum number of children)
- non-leaf nodes store $\leq M-1$ keys (for search)
- root either is a leaf or has $[2,M]$ children
- All non-leaf (not root) nodes have $[\lceil M/2 \rceil, M]$ children
- All leaves are at the same depth
- Leaves have $[\lceil L/2 \rceil, L]$ data entries

($M$ and $L$ depend on block size)

## 6.2 Definition (Multi-way Tree / M-way Tree)
A tree where each node can have $M$ children

Access time:
$$
\log_M(n)= \frac{\log_2 (n)}{\log_2(M)}
$$
(Generally used $M\approx 2^8 \approx 200$)

## 6.3 Example (B-Tree)
![[Pasted image 20210225115330.png]]
where $M=5$ and $L=5$

Insertion works by going down if it's inbetween the values. If the leaf cannot store more data the procedure is as follows:
1. move up the tree until there is a free spot
2. once a free spot is found, find the mid value in the level below the free spot and drag it and it's associated subtree up to that level
3. try inserting again


## 6.4 Definition (Tries)
Trees with a possible branch for every letter of an alphabet
Memory trade-off for time complexity

## 6.5 Example (Tries)

Un-collapsed Trie:
![[Pasted image 20210225122019.png]]
- all *actual* words end with a special letter "$"

Collapsed Trie:
![[Pasted image 20210225122145.png]]

## 6.6 Definition (Suffix Trees)
A trie of all suffixes of a string
Memory & time complexity: $\Theta(n)$

## 6.7 Example (Suffix Tree)

The string is "banana"
![[Pasted image 20210225123840.png]]
