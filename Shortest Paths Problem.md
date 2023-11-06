Input:
- [[Directed Graph]] $G=(V,E)$
- [[edge]] weights 
- start vertex $s$

Output
- The length of the shortest path from $s$ to $v$, denoted $d(v)$, for each $v\in V$.

>[!note]
>If the edge weights are all positive, there is a [[Greedy Paradigm]] [[Algorithm]] to solve this problem.

Dynamic Programming:
Attempt $1$:
Step 1: Let $\texttt{OPT}(v)$ be the length of the shortest [[Path]] from $s$ to $v$.

Step 2: $$\texttt{OPT}(v)=\min\{\texttt{OPT}(u)+w(u,v):u \text{ is a neighbor of }v\}$$where a neighbor is a vertex with an edge to $v$

Step 4: $\texttt{OPT}(s)=0$ would make this work for positive edge weights.

Attempt $2$:
[[Bellman-Ford Algorithm]]
