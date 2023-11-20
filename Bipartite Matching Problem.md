>[!def]
>A *matching* is a [[Set]] of [[edge]]s $M\subseteq E$ such that no two [[edge]]s in $M$ share an endpoint. 

>[!def]
>A matching $M$ is said to be a *perfect matching* if every vertex is matched.

Input:
- Bipartite [[Graph]] $G=(V,E)$

Output:
- Matching that includes a maximal amount of matching

>[!alg]
Step 1: Convert matching to a flow network
>1. Add two vertices $s,t$ to $V$.
>2. Make every edge directed from $A$ to $B$
>3. Add directed edges with capacity from source to every vertex in $A$
>4. Add directed edges with capacity to sink from every vertex in $B$
>5. Give all edges capacity 1
>
Step 2: Solve [[Max Flow Problem]] on this network
>
Step 3: Return the collection of original edges which have a flow of 1

>[!proof] Feasibility:




