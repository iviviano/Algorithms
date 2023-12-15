>[!note] 1

(a) idea: use max flow to find min cut. Add one to capacity of min cut. Keep track of which edges have been changed. Continue until $|f|=T$. If none of the edges crossing the min cut have been changed, this is a cut of capacity exactly $T$. (Does this guarantee there isn't one if some of the edges have changed?)

$$\begin{align*}
&\textbf{Algorithm } \text{Flow Size }T\\
&\textbf{Input: } \text{Graph }G=(V,E),\text{ capacities }c,\text{ integer }T\\
&\textbf{If } \texttt{max\_flow}(G,c)<T \textbf{ then:}\\
&\quad \textbf{return } \texttt{false}\\
&\textbf{While } |f=\texttt{max\_flow}(G,c)|\ne T \textbf{ do:}\\
&\quad \text{decrease the maximal }c \text{ values by }1\\
&\textbf{end while}\\
&\textbf{return } f
\end{align*}$$





(b)$$\begin{align*}
&\textbf{Algorithm } \text{Daycare}\\
&\textbf{Input: } \text{ min handlers }W_{i},\text{ max children }K_{j},\text{ compatible children }S_{j}\\
&\text{Let }V=\{s,t\},E=\emptyset\\
&d(v)=0,d(s)=0\\
&\textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad \text{Add }i \text{ to }V\\
&\quad d(i)=0\\
&\quad \text{Add }e=(s,t)\text{ to }E\\
&\quad c(e)=m\\
&\quad l(e)=W_{i}\\
&\textbf{end for}\\
&\textbf{For } n+1\le j\le n+m \textbf{ do:}\\
&\quad \text{Add }j \text{ to }V\\
&\quad d(j)=0\\
&\quad \text{Add }e=(j,t)\text{ to }E\\
&\quad c(e)=K_{j}\\
&\quad l(e)=0\\
&\quad \textbf{For } v\in S_{j} \textbf{ do:}\\
&\quad \quad \text{Add }e=(v,j)\text{ to }E\\
&\quad \quad c(e)=1\\
&\quad \quad l(e)=0\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\text{Add }e=(t,s)\text{ to }E\\
&c(e)=\sum_{j}K_{j}\\
&l(e)=0\\
&\text{Let }G=(V,E)\\
&\textbf{return } \exists \texttt{circulation\_lower\_bounds}(G,c,l,d)\\
\end{align*}$$

A matching of children to employees is a subset $M\subseteq\{1,\ldots,n\}\times\{n+1,\ldots,n+m\}$.

Suppose there is a valid circulation $s$ in $G$. Let $$M=\{(i,j):s((i,j))=1\text{ and }1\le i\le n,n+1\le j\le n+m\}$$Claim: $M$ is a valid matching of children to employees. We need the following:
1. $(i,j)\in M\implies i\in S_{j}$
2. For each $i$, $|\{(i,j)\in M\}|\ge W_{i}$
3. For each $j$, $|\{(i,j)\in M\}\le K_{j}$
(1) $M$ is a subset of $E$ and there are only edges from child $i$ to employee $j$ if $i\in S_{j}$.
(2) $l(s,i)=W_{i}$. Since $s$ is a valid circulation, $$\sum_{e \text{ into }i}s(e)-\sum_{e\text{ out of }i}s(e)=d(i)=0.$$and $$\sum_{e\text{ into }i}s(e)=s((s,i))\ge l((s,i))= W_{i}.$$Therefore, $$\sum_{e\text{ out of }i}s(e)\ge W_{i}.$$Since the only edges out $i$ go to employees, and each has capacity $1$, there must be circulation of $1$ on at least $W_{i}$ edges from $i$ to employees.
(3) $c(j,t)=K_{j}$. Since $s$ is a valid circulation, $$\sum_{e\text{ into }j}s(e)-\sum_{e\text{ out of }j}s(e)=d(j)=0$$and $$\sum_{e \text{ out of }j}s(e)=s((j,t))\le c((j,t))=K_{j}.$$Therefore, $$\sum_{e \text{ into }j}s(e)\le K_{j}.$$Since the only edges into $j$ come from children, and each has capacity 1, there must be circulation of 1 on at most $K_{j}$ edges from children to $j$. 

So, a valid circulation on $G$ implies there exists a valid matching.

Suppose there is a valid assignment $M$ of children to employees. Let a pair $(i,j)$ refer to child-employee edges only. Define a circulation $s$ on $G$ as follows:
1. $s(p)=1$ for all $p\in M$.
2. $s((i,j))=0$ $(i,j)\in E-M$
3. $$s((s,i))=\sum_{(i,j)\in E}s((i,j))$$
4. $$s((j,t))=\sum_{(i,j)\in E}s((i,j))$$
5. $$s((t,s))=\sum_{e \text{ into }t}s(e)$$
Claim: $s$ is a valid circulation: 
Demand constraint: the definition of $s$ trivially satisfies the demand constraint for all vertices except $s$. And since the demand of $s$ is 0, this implies that the circulation also satisfies the demand constraint for $s$. 
Capacity constraint: For all $(i,j)\in E$, $s((i,j))\le1=c((i,j))$. For all $i$, $$s((s,i))=\sum_{e \text{ into }i}s(e)=\sum_{e \text{ out of }i}s(e).$$Since each edge out of $i$ goes to an employee and satisfies the capacity constraint of 1, there is at most $m$ circulation leaving $i$. For all $j$, $$s((j,t))=\sum_{e \text{ out of }j}s(e)=\sum_{e \text{ into }j}s(e).$$Since the only incoming edges to $j$ are from children, and each has capacity 1, we need to show that at most $K_{j}$ circulation enters $j$. Since the matching was valid, at most $K_{j}$ children are matched to $j$. So by the definition of $s,$ $s((j,t))\le K_{j}$. Since edge into $t$ satisfies the demand constraint, $$s((t,s))=\sum_{e \text{ into }t}s(t)\le\sum_{j}K_{j}.$$
Lower bound constraint: For all $(i,j)\in E$, $s((i,j))\ge0=l((i,j))$. For all $j$, $l((j,t))=0$, so it is satisfied trivially. The same holds for $(t,s)$. For all $i$, $$s((s,i))=\sum_{e \text{ into }i}s(e)=\sum_{e \text{ out of }i}s(e).$$Since the only outgoing edges from $i$ are to employees, and each has capacity 1, we need to show that at least $W_{i}$ circulation enters $i$. Since the matching was valid, at least $W_{i}$ children are matched to $i$. So, by the definition of $s,$ $s((s,i))\ge W_{i}$. 

So, a valid matching implies there exists a circulation on $G$.

Therefore, the algorithm returns $\texttt{true}$ $\iff$ there is a valid matching.

(c) $$\begin{align*}
&\textbf{Algorithm } \text{Specialist Daycare}\\
&\textbf{Input: } \text{min handlers }W_{i},\text{ max children }K_{j},\text{ compatible children }S_{j},\text{ and specialties }A,B,C\\
&\text{Let }G=(V,E)\text{ be a graph}\\
&\text{Let }V=\{s,t\},E=\emptyset\\
&\textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad \text{Add a vertex }i \text{ to }V\\
&\quad \text{Add an edge }e=(s,i)\text{ to }E\\
&\quad c_{A,B,C}(e)=1\\
&\textbf{end for}\\
&\textbf{For } n+1\le j\le n+m \textbf{ do:}\\
&\quad \text{Add a vertex }j \text{ to }V\\
&\quad \text{Add an edge }e=(j,t)\text{ to }E\\
&\quad c_{A,B,C}(e)=K_{j}\\
&\quad \textbf{For } i\in S_{j} \textbf{ do:}\\
&\quad \quad \text{Add an edge }e=(i,j)\text{ to }E\\
&\quad \quad \textbf{If } j\in A \textbf{ then:}\\
&\quad \quad \quad c_{A}(e)=1\\
&\quad \quad \quad c_{B,C}(e)=0\\
&\quad \quad \textbf{If } j\in B \textbf{ then:}\\
&\quad \quad \quad c_{B}(e)=1\\
&\quad \quad \quad c_{A,C}(e)=0\\
&\quad \quad \textbf{If } j\in C \textbf{ then:}\\
&\quad \quad \quad c_{C}(e)=1\\
&\quad \quad \quad c_{A,B}(e)=0\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\text{Let }f_{A}=\texttt{max\_flow}(G,c_{A})\\
&\text{Let }f_{B}=\texttt{max\_flow}(G,c_{B})\\
&\text{Let }f_{C}=\texttt{max\_flow}(G,c_{c})\\
&\textbf{If } |f_{A}|\ne n\lor|f_{B}|\ne n\lor |f_{C}|\ne n \textbf{ then:}\\
&\quad \textbf{return } \texttt{false}\\
&\text{Let }f=f_{A}+f_{B}+f_{C}\\
&\textbf{For } n+1\le j\le n+m \textbf{ do:}\\
&\quad \text{Let }S'_{j}=\emptyset\\
&\quad \textbf{For } i\in S_{j} \textbf{ do:}\\
&\quad \quad \textbf{If } !f((i,j)) \textbf{ then:}\\
&\quad \quad \quad \text{Add }i \text{ to }S_{j}'\\
&\quad \quad \textbf{end if}\\
&\quad \textbf{end for}\\
&\quad K_{j}'=K_{j}-f((j,t))\\
&\textbf{end for}\\
&W_{i}'=W_{i}-3\\
&\textbf{return } \texttt{daycare}(W_{i}',S_{j}',K_{j}')\\
\end{align*}$$
>[!proof]

Suppose there is a valid matching, and let $M$ be such a matching. Then, there must be a way to assign each child to each specialist. I will show that $|f_{A}|=n$. By symmetry this will also imply that $|f_{B}|=|f_{C}|=n$. 

Define a flow $f$ on $G$ as follows: 
1. For all $i$, $f((s,i))=1$
2. For each $i$, pick $(i,j)\in M$ with $j\in A$, and let $f((i,j))=1$. For all other $(i,j)\in E$, $f((i,j))=0$
3. For all $j$, $$f((j,t))=\sum_{e \text{ into }j}f(e)$$
Then, $$|f|=\sum_{e \text{ out of }s}f(e)=n$$since there are $n$ children, so we must show that $f$ is a valid flow. 

Conservation constraint: for each $i$, there is only one edge in. This has flow $1$. Only one edge out has flow, and this edge also has flow 1. The conservation constraint is trivially satisfied for all $j$ by the definition of $f$. 

Capacity constraint: for all $i$, $f((s,i))=1=c((s,i))$. For all $(i,j)\in E$, $f((i,j))\le1=c((s,i))$. For all $j$, $$f((j,t))=\sum_{e \text{ out of }j}f(e)=\sum_{e \text{ into }j}f(e).$$Since the only incoming edges to $j$ are from children, and each capacity 1, we must only show that at most $K_{j}$ incoming edges have flow. An incoming edge $(i,j)$ has flow 1 only if $(i,j)\in M$. Since $M$ is a valid matching, there are at most $K_{j}$ of these edges.

Note that $f$ is the max flow on $G$ with capacities $c_{A}$, so there exists a flow $f_{A}$ with $|f_{A}|=n$.

So if there is a valid matching, we pass the $\textbf{If } |f_{A}|\ne n\lor|f_{B}|\ne n\lor |f_{C}|\ne n \textbf{ then:}$ line. Now, we must show that $\texttt{daycare}(W_{i}',S_{j}',K_{j}')$ returns $\texttt{true}$. We know that there is a valid matching that assigns each child $W_{i}$ employees. Since we have already assigned each child 3 employees, there is still a valid assignment of at least $W_{i}-3$ employees. We know that there is a valid assignment that assigns each employee only children in $S_{j}$. By removing only the children already assigned to employee $j$ from $S_{j}$, we may still complete the valid assignment with $S_{j}'$. We know that there is a valid assignment that assigns each employee at most $K_{j}$ children. $f((j,t))$ is the number of children assigned to employee in the specialty fulfilling step. We may still complete the valid assignment as long as we assign at most $K_{j}-f((j,t))$ children to employee $j$. Therefore, $\texttt{daycare}(W_{i}',S_{j}',K_{j}')$ returns $\texttt{true}$.


Suppose the algorithm returns $\texttt{true}$. I will show that a valid matching exists. 

Claim: The pairs $(i,j)$ for which $f((i,j))=1$ form a sub-matching for which 
1. each child is matched to an employee of each specialty
2. no employee is assigned to a non-compatible child
3. no employee is matched to too many children
(1) Since $|f_{A}|=n$, $f_{A}((s,i))=1$ for all $i$. By the conservation constraint, $$f_{A}((s,i))=\sum_{e \text{ into }i}f_{A}(e)=\sum_{e \text{ out of }i}f_{A}(e).$$So, there exists $j$ such that $f_{A}((i,j))=1$. By the capacity constraint, this is only possible if $j\in A$. Therefore, $i$ is matched to an employee specializing in $A$, and similarly for $B$ and $C$.
(2) This is obvious from the definition of $G$. A pair $(i,j)$ is in $E$ only if $i\in S_{j}$. Since the sub-matching is a subset of $E$, this is true.
(3) Let $j$ be some employee, and suppose $j\in A$ without loss of generality. Clearly, the flow $f$ on all edges into or out of $j$ is equal to $f_{A}$. So, $$K_{j}\ge f_{A}((j,t))=\sum_{e \text{ out of }j}f_{A}(e)=\sum_{e \text{ into }j}f_{A}(e)=\sum_{e \text{ into }j}f(e).$$Since the only incoming edges to $j$ are children, and each edge has capacity 1, at most $K_{j}$ incoming edges have flow 1. So, at most $K_{j}$ children are assigned to employee $j$.

To complete the matching, we must just assign each child sufficiently many employees, without violating any other conditions of matching. We still need to assign each child $W_{i}-3=W_{i}'$ employees. Since we can do this with only the remaining employee assignments and capacities (this is exactly what it means for $\texttt{daycare}(W_{i}',S_{j}',K_{j}')$ to return $\texttt{true}$), there is a valid matching. 


Therefore, the algorithm returns $\texttt{true}$ $\iff$ there is a valid matching.

>[!note] 2

$$\texttt{OPT}(i,j)=l(j)-l(i)-1+\max\{\texttt{OPT}(i+1,j),\texttt{OPT}(i,j-1)\}$$
Base cases: $\texttt{OPT}(i,i)=0$ for all $i$. 

Goal: compute $\texttt{OPT}(0,k+1)$



>[!note] 3

(a) Let $V=\{v\}$ and $E=\emptyset$. If $k=1$ and $W=2$, then the solution is $S=V$. Since there are no pairs of vertices in this set, the weight condition is vacuously true.

IMAGE

(b) Let $V=\{v,t\}$ and $E=\{\{v,t\}\}$. Let $w_{e}=1$ for $e\in E$. If $k=2$ and $W=2$, there is no solution. The only subset of size 2 of $V$ is $V$. However, $w_{e}=1<W$ for $e=\{v,t\}$ and $\{v,t\}\subseteq V$. 

IMAGE

(c)

Let $P_{i}$ be a collection of paths. We want to know if there are $k$ paths that don't overlap.

Make a vertex $i$ for each $P_{i}$. For each $i,j$, add an edge $e=\{i,j\}$. Let $w(e)=1$ if $P_{i}\cap P_{j}=\emptyset$ and $w(e)=0$ if $P_{i}\cap P_{j}≠\emptyset$.

Return true iff there is a collection of $k$ vertices such that the weight of any edge between them is at least 1.



I will refer to this problem as weighted net.

In $NP$:
Certificate: A subset $K\subseteq V$.
Certificate:
1. Is $|K|=k$
2. For all pairs $\{v,t\}\subseteq K$, is $w_{e}\ge W$ for $e=\{v,t\}$?
It is constant to check the size of $K$. There are less than $|K|^2$ pairs in $K$. So, this is a polynomial time certificate.

In $NP$-Hard:

Claim: restroom nightmare $\le_{p}$ weighted net

$$\begin{align*}
&\textbf{Algorithm } \text{Reduce restroom nightmare to weighted net}\\
&\textbf{Input: } \text{Graph }G=(V,E),\text{ stations }s_{i},\text{ bathrooms }P_{i},\text{ paths }P_{i},\text{ integer }k\\
&\text{Let }H=(S,T)\\
&\text{Let }S=\{i:i\text{ is a guard}\}\\
&\text{Let }T=\{\{v,t\}:v,t\in S \text{ and }v\ne t\}\\
&\textbf{For } e=\{v,t\}\in T \textbf{ do:}\\
&\quad \textbf{If } P_{v}\cap P_{t}=\emptyset \textbf{ then:}\\
&\quad \quad w_{e}=1\\
&\quad \textbf{Else:}\\
&\quad \quad w_{e}=0\\
&\quad \textbf{end if}\\
&\textbf{end for}\\
&\textbf{return } \texttt{weighted\_net}(H,w,k,W=1)\\
\end{align*}$$
Suppose that $\texttt{weighted\_net}(G,w,k,W)$ returns $\texttt{true}$ $\iff$ there is a subset of vertices of size $k$ such that for each pair of vertices in this set, the edge connecting them has weight at least $W$.

Suppose there is a set $K$ of $k$ guards such that for all $i,j\in K$ with $i\ne j$, $P_{i}\cap P_{j}=\emptyset$. Then, $K\subseteq S$ has $k$ vertices. For each $\{v,t\}\subseteq K$, $P_{v}\cap P_{t}=\emptyset$. Therefore, $w_{\{v,t\}}=1$. Thus, $K$ is a subset of $k$ vertices such that the edge connecting each pair has weight at least $W=1$. So, the algorithm returns $\texttt{true}$.

Suppose the algorithm returns $\texttt{true}$. Let $K\subseteq H$ with $|K|=k$ and for all pairs of vertices $e=\{v,t\}\subseteq K$, $w_{e}\ge1$. 