Idea: How much traffic can we route through our network?

Input: A flow network
- Directed [[Connected Graph]] graph: $G=(V,E)$
- Source $s$, with only outgoing edges
- Sink $t$, with only incoming edges
- Capacities $c(e)≥0$ for each edge $e\in E$
	- largest possible flow through $e$

>[!def]
>A *flow* is a value $f(e)$ for each edge $e\in E$ satisfying a capacity constraint $0≤f(e)≤c(e)$ and a conservation constraint: $$\forall v\in V-\{s,t\}:\sum_{e \text{ into }v}f(e)=\sum_{e \text{ out of }v}f(e)$$

Output: a flow that maximizes $$\sum_{e \text{ out of }s}f(e)$$

>[!def]
>Given a flow $f$, we can construct the *residual graph* $G_{f}=(V,E_{f})$ with capacities $c_{f}$ in the following way. For each edge $e=(u,v)\in E$:
>1. If $f(e)<c(e)$, add $e$ to $E_{f}$ with $c_{f}(e)=c(e)-f(e)$. Then, $e$ will be called a *forward edge*
>2. If $f(u,v)>0$, where $e=(u,v)$, let $e'=(v,u)$. Add $e'$ to $E_f$. If $e'\notin E$, $c_{f}(e')=f(e)$. Otherwise, $c_{f}(e')=c(e')+f(e)$. Then, $e'$ will be called a *backwards edge*

Flow Augmentation:
Given flow $f$, and residual graph $G_{f}$, can augment $f$ by 
1. find [[Path]] $s \rightarrow t$ in $G_{f}$ by [[Breadth-First Search]]
2. let $b$ be a bottleneck capacity of $P$ (smallest capacity in $G_{f}$)
3. Push $b$ additional flow along forward edges of $P$
4. Undo $b$ flow on back edges of $P$

>[!note]
>1. Augmentation maintains feasibility
>2. Flow must increase with augmentation

>[!alg] Ford-Fulkerson Algorithm
>$$\begin{align}
&f=\text{null flow}\\
&G_{f}=G,c(e)\\
&\textbf{While } \text{There exists an } s \rightarrow t \text{ path }P \text{ in }G_{f}\textbf{ do:}\\
&\quad \text{Augment }f \text{ along }P\\
&\quad \text{update }G_{f}\text{ using new flow}\\
&\textbf{end while}\\
&\textbf{return } f\\
\end{align}$$

Runtime:
Assume capacities are integers. 

There are at most $C=\sum c(e)$ iterations. 

Each iteration, must find bottleneck capacity, choose a path, augment the flow, and update the residual graph.

Finding an $s \rightarrow t$ path is $O(m)$ through a [[Breadth-First Search]] on a [[Connected Graph]] [[Graph]]. 

Finding the bottleneck in the path is $O(n)$, since a path is at most $n-1$ edges.

Augmenting the path is $O(n)$ for the same reason.

Updating the residual graph is $O(m)$, since there are at most $m$ edges that need to be updated. 

Therefore, the total runtime is $O(mC)$.

>[!proof] Proof of Optimality

Idea: 
1. Identify upper bound on max flow
2. Show FF constructs flow that meets this upper bound

>[!def]
>For a [[Cut]] $(A,B)$ of $G$, define the *capacity* of $(A,B)$ to be $$\sum_{(a,b)\in E:a\in A,b\in B}c(e)$$

Our upper bound will be $$B=\min\{C((A,B)):(A,B)\text{ is a cut of }G\}$$

>[!prop] Lemma
For all $s-t$ cuts $(A,B)$ and flow $f$,$$|f|=\sum_{e \text{ into }b}c(e)-\sum_{e \text{ out of }b}c(e)$$

$$|f|=\sum_{e \text{ into }B}f(e)-\sum_{e \text{ out of }B}f(e)≤\sum_{e\text{ into }B}f(e)≤\sum_{e \text{ into }B}c(e)=C((A,B))$$
so, $B$ is an upper bound for $|f|$.

