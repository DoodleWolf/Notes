## 7.1 Definition (Direct-address tables)
An array where each slot is represented by a key
- works for small sizes (since there are many possible keys there will be many empty spaces)

## 7.2 Implementation (Direct-address table)
![[Pasted image 20210226150228.png]]

## 7.3 Definition (hash function)
A funtion $h(k): U \rightarrow \{0, \dots, m-1 \}$ where $U$ is all possible keys (universe) and $m$ is the size of the hashtable 

## 7.4 Notes (on hash functions)
- they allow us to handle only a certain amount of keys instead of the whole range
- a "random"-looking hash function can minimize collisions
- hash function cause collisions when two seperate keys generate the same index
- each slot stores the key and the value, on search the algorithm would check the possible places it could be and whether the key matches

## 7.5 Definition (chaining)
All elements that hash to the same place in the array are placed in a linked list
![[Pasted image 20210226151505.png]]

## 7.6 Implementation (chaining)
![[Pasted image 20210226151835.png]]

Note: deletion can be done $O(1)$ when using doubly-linked lists as you are given element $x$ and don't need to search for it

## 7.7 Definition (load factor)
$\alpha$ (or in lectures $\lambda$) for hash table $T$ as $\frac nm$ where $m$ is the array size and $n$ is the amount of elements.

## 7.8 Definition (simple uniform hashing)
The assumption that any given element is equally likely to hash into any of the $m$ slots.

## 7.9 Theorem (time complexity of collision search)
An unsuccesful/succesful search takes expected time $\Theta (1+ \alpha)$ in hash table using chaining assuming simple uniform hashing.

#### proof
For an unsuccesful key $k$ the algorithm must search the linked list to the end whose expected value is $E[n_{h(k)}]=\alpha$ plus the time it takes to compute $h(k)$ => $\Theta(1 + \alpha )$

For a succesful key $k$ we use probablity. The expected number of elements the algorithms will go through is all the elements $n$ plus the elements added after our element (into the linked list)
![[Pasted image 20210227120415.png]]
- $X_{ij}$ represents the probability of the two keys being the same? (key $i$ and key $j$ being the same)
- getting $\Theta(1 + \alpha)$

## 7.10 Defintion (division method)
The hash function maps a key $k$ into one of $m$ slots via
$$
h(k)=k \mod m
$$
- a prime not too close to $2$ is a good choice for $m$
- using $2^p$ as $m$ will result in cutting low order bits

## 7.11 Definition (multiplication method)
Using a constant $A \in (0,1)$, the hash function maps a key $k$ into one of $m$ slots via
$$
h(k) = \lfloor m (k A \mod 1) \rfloor
$$
where $kA \mod 1 \equiv kA - \lfloor kA \rfloor$ 
- $m$ can be anything
- a good implementation would be $m=2^p$ and $A=\frac {s}{2^w}$ where $0 < s< 2^w$ and $w$ is the word size, the result would be a $r_12^w+r_0$. The hashed key would $p$ bits of $r_0$
- Knuth suggest $A \approx (\sqrt{5} - 1)/2$

## 7.12 Definition (universal hashing)
A form of hashing keys in which a hash function is chosen randomly independent of what the key is therefore guaranteeing that the same key will not go into the same slot
- the function gets randomized on initialization
- $\Theta (1+ \alpha)$ search
- $\Theta(1)$ insert/delete/search

## 7.13 Definition (open addressing)
All elements are stored on the hash table itself (no linked lists)
- $alpha$ cannot exceed $1$
- hash function returns a sequence of position (see more in probe)
$h : U \times \{0, \dots, m-1\} \rightarrow \{0, \dots, m-1\}$

## 7.14 Definition (probe)
A way to handle collisions in which each key has a probe sequence which it can go to if there is a collision. The probe sequence must be a permutation of all possible hash-table positions.
- there must be a special "deleted" value available

## 7.15 Implementation (probe-insert)
![[Pasted image 20210227170304.png]]

## 7.16 Implementation (probe-search)
![[Pasted image 20210227170340.png]]


## 7.17 Definition (linear probing)
$$
h(k,i)=(h'(k)+i) \mod m \text{ for } i=0, \dots, m-1
$$
Nutshell: keep moving up by one till an empty spot is found
Note: Results in primary clustering, long runs of occupied slots get longer thus increasing search time


## 7.18 Definition (quadratic probing)
$$
h(k,i)=(h'(k)+c_1i+c_2i^2) \mod m \text{ for } i=0, \dots, m-1
$$
$c_1, c_2$ are constants
Note: results in secondary clustering (?)

## 7.19 Defintion (double hashing)
$$
h(k,i)=(h_1(k)+ih_2(k)) \mod m \text{ for } i=0, \dots, m-1
$$
$h_1, h_2$ are auxilary hash function.

Note: $h_2 (k)$ must be relatively prime to $m$ to cover the whole hash table

## 7.20 Theorem
 The expected number of probes in an unsuccesful search is at most $\frac{1}{1-a}$
 
 #### proof
 See Cormen pg. 242
 Hinges on being an infinite power series sum since the probability of $i$ succesive failures is $\frac nm \cdot \dots \cdot \frac {n-i+2}{m-i+2} \leq \left( \frac nm \right)^{i-1}$
 
 ## 7.21 Theorem
The expected number of probes in a successful search is at most $\frac 1a \ln{\frac {1}{1-a}}$

#### proof
$$
\begin{align}
E[X] &= \frac 1n \sum \limits_{i=0}^{n-1} \frac{m}{m-i} \\
& = \frac 1\alpha \left( \sum \limits_{j=1}^{m} \frac 1j-\sum\limits_{j=1}^{m-n}\frac 1j \right)\\
& \leq \frac 1\alpha \int \limits_{m-n}^m \frac 1x dx \\
& = \frac 1\alpha \ln{ \frac {m}{m-n}} \\
& = \frac 1\alpha \ln{ \frac {1}{1-\alpha}}
\end{align}
$$

## 7.22 Definition (Perfect hashing)
A hashing technique where the worst-case number of memory accesses required to perform a search is $O(n)$
- Use a secondary hash table to handle collisions instead of a linked list

## 7.23 Theorem 
Hash tables of size $m=n^2$ using a universal hash function have a collision chance of $\frac 12$

## 7.24 Theorem
$$
E \left[ \sum \limits_{j=0}^{m-1} n_j^2 \right] < 2n
$$
where $n_j$ is the number of keys hashing ot slot $j$