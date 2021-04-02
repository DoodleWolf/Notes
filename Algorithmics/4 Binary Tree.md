# Tree
**tree**: acyclic graph
 **rooted tree**: imposing an ordering on the nodes
**children**: nodes immediately beneath them
![[Pasted image 20210216120514.png]]

## levels
![[Pasted image 20210216120649.png]]
height of a tree: number of levels

## Binary Trees
Definition: a tree where each node can have zero, one or two children

Most nodes possible: $2^h-1$ where $h$ is the height

![[Pasted image 20210216202811.png]]
takes $\Theta (n)$ time to print whole thing

Methods:
- contains(node)
- add(node)
- remove(node)

## Java Code

#### Tree
![[Pasted image 20210224175019.png]]

#### Inorder Tree walk 

(Recursive) - $\Theta(n)$
![[Pasted image 20210224180621.png]]

(Non-Recursive) - $\Theta(n)$
![[Pasted image 20210224181153.png]]


#### finding an element - $\log_2(n)$
![[Pasted image 20210224183026.png]]

#### remove
![[Pasted image 20210224194741.png]]
![[Pasted image 20210224194809.png]]



## Speed of Search

Worst case scenario: the height of the tree $\log_2(n)$


## Tree Iterators
**Tree Iterator< T >**
Methods:
- boolean hasNext()
- T next() : finds successor node
- void remove()

T next():
![[Pasted image 20210224192832.png]]



## Balancing 

Tree depth:
- worst case: $\Theta (n)$
- average case: $\log(n)$ (for random sequence)
- best case: $\log(n)$


Change the tree depth with rotations:
![[Pasted image 20210224195533.png]]
![[Pasted image 20210224195806.png]]

Double rotation

Java code for rotation:
![[Pasted image 20210224195842.png]]

Strategies for balancing:
1. **AVL trees**: binary tree where the height of left and right subtree differ height by at most 1 and the subtrees are AVL trees
2. **Red-black trees**: coloring nodes red and black where red children must be black and all paths root to nodes have to have the same amount of black nodes
3. **Splay trees**


## AVL Tree

min. number of nodes in an AVL tree of height $h$:
where $m(1)=1$ and $m(2)=2$
$$
m(h)=m(h-1)+m(h-2)+1
$$
![[Pasted image 20210224201530.png]]

Look similar to fibonacci sequence $f(h)=f(h-1)+f(h-2)$

### theorem (minimum node for height function)

$$
m(h)=f(h+2)-1
$$

#### proof
Induction:
1. base case (too lazy to check $m(2)$)
$$
m(1)=f(1+2)-1=2-1=1=m(1)\ \checkmark
$$
2. assume $n=k$ case
$$
m(k)=f(k+2)-1
$$
3. prove $n=k+1$ case
$$
\begin{align}
m(k+1) &=m(k+1-1)+m(k+1-2)+1 \\
&=f(k+2)-1+f(k+1)-1+1 \\
&=f(k+3)-1 \ \checkmark \\
\end{align}
$$


### theorem ($\log$ complexity)
AVL tree will always have $\log$ depth, hence $\Theta(n)$ complexity

#### proof
![[Pasted image 20210224204601.png]]


### implementation

AVL tree is a binary search tree with extra info at each node about balance (balancefactor = height left tree - height right tree)

RotateRight for positive imbalance (and equal signs or $0$?)
![[Pasted image 20210224205903.png]]
RotateLeft for negative imbalance (and equal signs or $0$?)
![[Pasted image 20210224205846.png]]
LeftRight when the signs are $-$ then $+$ (?)
RightLeft  when the signs are $+$ then $-$ (?)
![[Pasted image 20210224205747.png]]


upon adding an element:
1. add the element
2. calculate balance factor of the subtree and stop when $\pm 1 <$ balanceFactor to re-balance tree
3. if balance factor goes to zero stop


### Performance
![[Pasted image 20210224211530.png]]


## Red-Black Trees

Red rule: the children of a red node have to be black
Black rule: all paths from root to node (no children or with one child) have the same number of black nodes

#### properties
1. all nodes are red or black
2. the root is black
3. every leaf (nil) is black
4. red nodes only have black children
5. From each  path starting at the node down to a leaf there are the same number of black nodes

#### insertion
1. insert it first like a normal BST
2. if root make black other wise red
3. if parent is red we relabel or restructure
	- relabel (flip colors of parent & uncle & grandparent) if "uncle" exists and is red
	- rotate if "uncle" does not exist or is black


#### performance
![[Pasted image 20210224214839.png]]


