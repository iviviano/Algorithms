>[!def]
>A *matching* is a [[Set]] of [[edge]]s $M\subseteq E$ such that no two [[edge]]s in $M$ share an endpoint. 

>[!def]
>A matching $M$ is said to be a *perfect matching* if every vertex is matched.

Input:
- Bipartite [[Graph]] $G=(V,E)$

Output:
- Matching that includes a maximal amount of matching

Step 1: Convert matching to a flow network
1. Add two vertices $s,t$ to $V$.
2. Make every edge directed from $A$ to $B$
3. Add directed edges from source to every vertex in $A$
4. Add directed edges to sink from every vertex in $B$
5. 
