# Dijkstra's algorithm
### Problem
Given a starting node on a weighted graph find the shortest distance to all nodes

### Solution
1. Start at node $v_0$
2. Initialize table with distances to each node ($v_0 = 0$ the rest should be inifity as we haven't gotten distance yet)
3. Iteration (till all nodes have been gotten) start with $v_0$:
	1. get all neighbors of our current node
	2. look compare the distance to the neighbors and the distance you get from going to the current then the neighbor
	3. all lesser distances get updated


## Additional information
- J.A. Bondy and U.S.R Murty, Graph Theory with Application (Chapter 5)
- Shimon Even, Graph Algorithms (Chapter 6)