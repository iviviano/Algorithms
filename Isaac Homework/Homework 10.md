>[!note] 1

Ployride is in $NP$: 
- Certificate: a collection $P\subseteq E$
- Certification: 
	1.  $$\sum_{e\in P}c_{e}≥k$$
	2. For all $e=(u,v)\in P$, either
		1. $u=s$ and $v=t$
		2. $u=s$ and $(v,\_)\in P$
		3. $v=t$ and $(\_,u)\in P$
		4. $(\_,u)\in P$ and $(v,\_)\in P$
	3. $(s,\_)\in P$ and $(\_,t)\in P$

Let $n=|P|$.
Step 1 is $O(n)$, since it is a sum of $n$ terms. Step 2 is $O(n^2)$, since for each edge in $P$, we must look for other elements in $S$ satisfying certain conditions. Step 3 is $O(n)$, since we must just check that two elements are contained in $P$. Therefore, there exists a polynomial runtime certification for ployride.

In [[NP-Hard]]:
Reduce [[Hamiltonian Cycle Problem]] to Ployride:

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
&\textbf{return } \forall t\in V-\{s\}:\texttt{Ployride}(G,c,s,t,|V|-1)
\end{align*}$$

>[!proof]

Assume that $\texttt{Ployride}(G,c,s,t,k)$ returns true $\iff$ there is a simple path in the directed graph $G$ with edge costs given by $c$ with total cost of at least $k$. I will prove that the algorithm returns true $\iff$ $G$ has a Hamiltonian cycle.

Suppose $G$ has a Hamiltonian cycle.

Then, there is an ordering of the vertices $v_{1},\ldots,v_{n}$ such that $(v_{i},v_{i+1})\in E$ for all $i$ and $(v_{n},v_{1})\in E$. Since $(s,v_{1})\in E$ and $(v_{i},v_{i+1})\in E$ for all $i$, $$s,v_{1},v_{2},\ldots,v_{n}$$is a path in $G$ that starts at $s$ and ends at $v_{n}$. Since $(s,v_{2})\in E$, $(v_{i},v_{i+1})\in E$ for all $i$ and $(v_{n},v_{1})\in E$, $$s,v_{2},v_{3},\ldots,v_{n},v_{1}$$is a path in $G$ that starts at $s$ and ends at $v_{1}$. For all $i$, since $(s,v_{i})\in E$, $$s,v_{i},v_{i+1},\ldots,v_{n},v_{1},\ldots,v_{i-1}$$is a path in $G$ that starts at $s$ and ends at $v_{i}$. All of these paths consist of $n+1$ vertices ($n$ edges). So, the total cost of each path is $n$, since each edge has cost 1. Therefore, there is a path costing $n$ from $s$ to $v$ for all $v\in V-\{s\}$. So, $$\forall t\in V-\{s\}: \texttt{Ployride}(G,c,s,t,n)=\texttt{true}$$Since $|V|-1=n$, the algorithm returns $\texttt{true}$.


Suppose the algorithm returns $\texttt{true}$. Then, for each $i,$ there exists a path containing every vertex that starts at $s$ and ends at $v_{i}$. 


Claim: if there are paths of length $n$ to $k$ vertices, there is a cycle of $k$ vertices. 

Note that I am paths of length $n$ refer to paths from the $s$.

Base case: $k=1$. The base case holds trivially, since a single vertex is a cycle of $k$ vertices.

Inductive step: Suppose for some $k$ that if there are paths of length $n$ to $k$ vertices, there is a cycle of $k$ vertices. Suppose there are paths of length $n$ to $k+1$ vertices. Let $v_{1},\ldots,v_{k}$ be a cycle in that order. Let $v\ne v_{i}$ for all $i$ with a path of length $n$ to $v$. We have a path that goes through all of the vertices to $v$. Let $j$ be the index of the last of the vertices $v_{1},\ldots,v_{k}$ visited by this path.  



>[!note] 2


In [[NP]]:
- [[Certificate]]: A subset $S$ of the guards
- [[Certification]]: $|S|\ge k$, for all $i,j\in S,P_{i}\cap P_{j}=\emptyset$
This is [[Polynomial Run Time]], since there are less than $n^{2}$ pairs of elements of $S$ (where $n$ is the number of guards). To check that each pair of elements of $S$ is disjoint is constant.


In [[NP-Hard]]:

$$\begin{align*}
&\textbf{Algorithm } \text{Reduce 3D Matching to Nightmare at the Museum}\\
&\textbf{Input: } \text{Sets }X,Y,Z \text{ of size }n, \text{ matching set }T\subseteq X\times Y\times Z\\
&\textbf{Output: } \text{Is there a matching of size }n?\\
&\text{Let }G=(V,E)\text{ be an undirected graph}\\
&\text{Let }V=X\sqcup Y\sqcup Z\\
&\text{Let }E=\{\{s,t\}:s,t\in V \text{ and }s\ne t\}\\
&i=1\\
&\textbf{For } P=(x,y,z)\in T \textbf{ do:}\\
&\quad s_{i}=x\\
&\quad P_{i}=P\\
&\quad t_{i}=z\\
&\quad i++\\
&\textbf{end for}\\
&\textbf{return } \texttt{Nightmare}(G,s,P,t,|X|)
\end{align*}$$

>[!proof]
Assume that $\texttt{Nightmare}(G,s,P,t,k)$ returns $\texttt{true}$ $\iff$ there is a subset $S\subseteq I$ with $|S|\ge k$ and for any $i,j\in S$, $P_{i}\cap P_{j}=\emptyset$. I will show that the algorithm returns $\texttt{true}$ $\iff$ there is a matching of size $n$.
>
Let $I=\{n\in \mathbb{N}:n\le|T|\}$. Note: each $P_{i}$ is a path in $G$, since every vertex in $G$ is connected to every other vertex in $G$. 
>
Suppose the algorithm returns $\texttt{true}$. Let $S\subseteq I$ with $|S|\ge n$ and for all $i,j\in S$, $P_{i}\cap P_{j}=\emptyset$. Let $M=\{P_{i}:i\in S\}$. $|M|=|S|=n$. Since each $P_{i}\in T$, $M\subseteq T$. Additionally, if $P_{i},P_{j}\in M$, $P_{i}\cap P_{j}=\emptyset$. Therefore, $M$ is a valid matching with $n$ tuples. 
>
Suppose there is a valid matching $M$ of size $n$. Let $S=\{i\in I:P_{i}\in M\}$. Since $M\subseteq T$ and each $P_{i}\in T$, $|S|=|M|=n$. If $P_{i},P_{j}\in M$, $P_{i}\cap P_{j}=\emptyset$ , since $M$ is a valid matching. The existence of $S$ implies the algorithm returns $\texttt{true}$. 
>
Therefore, the algorithm is correct. 
