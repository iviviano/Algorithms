Idea: How much traffic can we route through our network?

Input: A flow network
- Directed [[Connected]] graph: $G=(V,E)$
- Source $s$, with only outgoing edges
- Sink $t$, with only incoming edges
- Capacities $c(e)≥0$ for each edge $e\in E$
	- largest possible flow through $e$

>[!def]
>A *flow* is a value $f(e)$ for each edge $e\in E$ satisfying a capacity constraint $0≤f(e)≤c(e)$ and a conservation constraint: $$\forall v\in V-\{s,t\}:\sum_{e \text{ into }v}f(e)=\sum_{e \text{ out of }v}f(e)$$

Output: a flow that maximizes $$\sum_{e \text{ out of }s}f(e)$$

>[!def]
>Given a flow $f$, we can construct the *residual graph* $G_{f}=(V,E_{f})$ with capacities $c_{f}$ in the following way. For each edge $(u,v)\in E$:
>1. If $f(e)<c(e)$, add $e$ to $E_{f}$ with $c_{f}(e)=c(e)-f(e)$
>2. 