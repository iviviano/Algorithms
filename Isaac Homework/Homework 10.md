>[!note] 1

Ployride is in $NP$: 
- Certificate: a collection $P\subseteq E$
- Certification: 
	1.  is $$\sum_{e\in P}c_{e}≥k?$$

Reduce [[Hamiltonian Cycle Problem]] to Ployride:

Let $G=(V,E)$ be a graph. 

$$\begin{align*}
&\textbf{Algorithm } \text{Reduce Hamiltonian Cycle to Ployride}\\
&\textbf{Input: } \text{Directed Graph }G=(V,E)\\
&\text{Add a vertex }s \text{ to }V\\
&\textbf{For } v\in V \textbf{ do:}\\
&\quad \text{Add an edge }(s,v)\text{ to }E\\
&\textbf{end for}\\
&\textbf{For } e\in E \textbf{ do:}\\
&\quad c_{e}=1\\
&\textbf{end for}\\
&\textbf{return } \forall t\in V-\{s\}\texttt{Ployride}(G,c,s,t,|V|-1)
\end{align*}$$

>[!proof]

Assume that $\texttt{Ployride}(G,c,s,t,k)$ returns true if there is a simple path in the directed graph $G$ with edge costs given by $c$ with total cost of at least $k$. I will prove that the algorithm returns true $\iff$ $G$ has a Hamiltonian cycle.

Suppose $G$ has a Hamiltonian cycle.

Then, there is an ordering of the vertices $v_{1},\ldots,v_{n}$ such that $(v_{i},v_{i+1})\in E$ for all $i$ and $(v_{n},v_{1})\in E$. Since $(s,v_{1})\in E$ and $(v_{i},v_{i+1})\in E$ for all $i$, $$s,v_{1},v_{2},\ldots,v_{n}$$is a path in $G$ that starts at $s$ and ends at $v_{n}$. Since $(s,v_{2})\in E$, $(v_{i},v_{i+1})\in E$ for all $i$ and $(v_{n},v_{1})\in E$, $$s,v_{2},v_{3},\ldots,v_{n},v_{1}$$is a path in $G$ that starts at $s$ and ends at $v_{1}$. For all $i$, since $(s,v_{i})\in E$, $$s,v_{i},v_{i+1},\ldots,v_{n},v_{1},\ldots,v_{i-1}$$is a path in $G$ that starts at $s$ and ends at $v_{i}$. All of these paths consist of $n+1$ vertices ($n$ edges). So, the total cost of each path is $n$, since each edge has cost 1. Therefore, there is a path costing $n$ from $s$ to $v$ for all $v\in V-\{s\}$. So, $$\forall t\in V-\{s\}: \texttt{Ployride}(G,c,s,t,n)=\texttt{true}$$Since $|V|-1=n$, the algorithm returns $\texttt{true}$.


Suppose $G$ does not have a Hamiltonian cycle and 

Suppose the algorithm returns $\texttt{true}$. Then, for all $t\in V-\{s\}$, there exists a path through all of the vertices in $V$ from $s$ to $t$. Let $v_{t}$ be the second vertex in such a path from $s$ to $t$. 

Claim: There exists $t\in V-\{s\}$ such that $(t,v_{t})\in E$. 




Pick $t$ by the claim. There is a path from $s$ to $t$ with $v_{t}$ as its second vertex. Therefore, there is a subpath from $v_{t}$ to $t$ with containing every vertex in the original $G$. Since $(t,v_{t})\in E$ as well, this is a Hamiltonian cycle.




>[!note] 2

