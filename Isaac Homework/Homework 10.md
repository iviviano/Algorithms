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
&\text{Let }t\in V\\
&\text{Add a vertex }s \text{ to }V\\
&\textbf{For } v\in V \textbf{ do:}\\
&\quad \text{Add an edge }(s,v)\text{ to }E\\
&\textbf{end for}\\
&\textbf{For } e\in E \textbf{ do:}\\
&\quad c_{e}=1\\
&\textbf{end for}\\
&\textbf{return } \texttt{Ployride}(G,c,s,t,|V|-1)
\end{align*}$$

>[!proof]

Assume that $\texttt{Ployride}(G,c,s,t,k)$ returns true if there is a simple path in the directed graph $G$ with edge costs given by $c$ with total cost of at least $k$. I will prove that the algorithm returns true if $G$ has a Hamiltonian cycle and false otherwise.

Suppose $G$ has a Hamiltonian cycle. Then, there is an ordering of the vertices $v_{1},\ldots,v_{n}$ such that $(v_{i},v_{i+1})\in E$ for all $i$ and $(v_{n},v_{1})\in E$. We may assume that $t=v_{n}$ (JUSTIFY). By adding $s$ to $V$ and the edge $(s,v_{1})$ to $V$, $$s,v_{1},\ldots,v_{n}=s,v_{1},\ldots,v_{n-1},t$$is a path in $V$. Since the cost of each edge is $1$ and this path has $n$ edges, there is a path cost $n$ in $G$. Since there are $n+1$ vertices in $s$, $\texttt{Ployride}(G,c,s,t,|V|-1)=\texttt{true}$.

Suppose $G$ does not have a Hamiltonian cycle. 

$s$ has no incoming edge, so any path containing every vertex in $V$ must start at $s$.



>[!note] 2


