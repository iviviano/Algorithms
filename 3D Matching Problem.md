3D Version of [[Bipartite Matching Problem]]

Input:
- $3$ [[Disjoint]] [[Set]]s $X,Y,Z$ each of size $n$
- A [[Set]] $T\subseteq X\times Y\times Z$ of size $m$

Output:
- a matching set $M\subseteq T$ such that each element of $X\sqcup Y\sqcup Z$ is in at most one element of $M$
- Does there exist a matching set of size $n$

In [[NP]]:
- [[Certificate]]: A [[Subset]] $M\subseteq T$
- [[Certification]]: Is $M$ of size $n$ and does $M$ have any elements sharing an element
Runtime: $O(n^2)$, look for each of $3n$ variables in $M$.

In [[NP-Hard]]:
Reduce [[3-SAT Problem]] to [[3D Matching Problem]]: