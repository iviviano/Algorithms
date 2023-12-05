>[!note] 1

(a) $s_{0}$ will satisfy the capacity constraint trivially, if $l(e)≤c(e)$ for all $e\in E$. Consider the graph $G=(V,E)$ with $V=\{1,2\}$ and $E=\{(1,2)\}$. Let $c(e)=l(e)=1$ for all $e\in E$ and $d(1)=d(2)=1$. Then, there is no circulation on $G$, since the capacities do not sum to $0$. In particular, the circulation $s_{0}$ cannot satisfy the demand constraint.

(b) 


Capacity constraint: Let $e\in E$. Since $s'$ is a valid circulation, $s'(e)\ge0$, so  $$s(e)=s'(e)+l(e)\ge l(e)$$So, $s$ satisfies all of the lower bounds. Since $s'$ is a valid circulation on $G'$, $s'(e)\le c'(e)=c(e)-l(e)$. So, $$s(e)=s'(e)+l(e)\le c(e)-l(e)+l(e)=c(e)$$ So, $s$ satisfies all of the upper bounds.

Demand constraint: Let $v\in V$. $$\begin{split}\sum_{e \text{ into }v}s(e)&-\sum_{e \text{ out of }v}s(e)=\sum_{e \text{ into }v}s'(e)+l(e)-\sum_{e \text{ out of }v}s'(e)+l(e)\\
&=\sum_{e \text{ into }v}s'(e)-\sum_{e \text{ out of }v}s'(e)+\sum_{e \text{ into }v}l(e)-\sum_{e \text{ out of }v}l(e)\\
&=\sum_{e \text{ into }v}s'(e)-\sum_{e \text{ out of }v}s'(e)+L(v)
\end{split}$$Since $s'$ is a valid circulation on $G'$, $$\sum_{e \text{ into }v}s'(e)-\sum_{e \text{ out of }v}s'(e)=d'(v)$$So, $$\sum_{e \text{ into }v}s(e)-\sum_{e \text{ out of }v}s(e)=d'(v)+L(v)=d(v)-L(v)+L(v)=d(v)$$Therefore, $s$ satisfies the demand constraint.

If we assume that $l(e)≥0$ for all $e\in E$, then $s(e)\ge s'(e)\ge0$. Therefore, $s$ is a valid circulation on $G$.

(c) 

Correct circulation: $s(e)=1$ for $e\in\{(\text{PIT } 8,\text{CLE }9),(\text{CLE }9:30,\text{MDW }11),(\text{PHL }7:30,\text{CLE }8:30),(\text{CLE }10,\text{ATL }12),(\text{CLE }9,\text{CLE }10),(\text{CLE }8:30,\text{CLE }9:30),(x,\text{PIT }8),(x,\text{PHL }7:30),(\text{MDW }11,y),(\text{ATL }12,y)\}$. $s(e)=0$ for all other $e$.


Correct circulation: $s(e)=1$ for $e\in\{(\text{CLE }9,\text{CLE }10),(\text{CLE }8:30,\text{CLE }9:30),(x,\text{PIT }8),(x,\text{PHL }7:30),(\text{MDW }11,y),(\text{ATL }12,y)\}$. $s(e)=0$ for all other $e$.


Correct flow: $f(e)=1$ for $e\in\{(\text{CLE }9,\text{CLE }10),(\text{CLE }8:30,\text{CLE }9:30),(x,\text{PIT }8),(x,\text{PHL }7:30),(\text{MDW }11,y),(\text{ATL }12,y)\}$. $f(e)=c(e)$ for all edges out of $s$ or into $t$. $f(e)=0$ for all other edges. 

>[!note] 2

$$\begin{align*}
&\textbf{Algorithm } \text{Hungry Hungry Hippies}\\
&\textbf{Input: } \text{People }p_{1},\ldots,p_{n}, \text{ Dining halls }d_{1},\ldots,d_{m},\text{ Sets }S_{i},\text{ Capacities }C_{j}\\
&\text{Construct a graph }G=(V,E)\\
&\text{Let }V=\{s,t,p_{1},\ldots,p_{n},d_{1},\ldots,d_{n}\},E=\emptyset\\
&\textbf{For } 1\le i\le n\textbf{ do:}\\
&\quad \text{Add }e=(s,p_{i})\text{ to }E\\
&\quad c(e)=1\\
&\quad \textbf{For } j\in S_{i} \textbf{ do:}\\
&\quad \quad \text{Add }e=(p_{i},d_{j})\text{ to }E\\
&\quad \quad c(e)=1\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\textbf{For } 1\le j\le m\textbf{ do:}\\
&\quad \text{Add }e=(d_{j},t)\text{ to }E\\
&\quad c(e)=C_{j}\\
&\textbf{end for}\\
&\text{Let }f=\texttt{MaxFlow}(G,c)\\
&\textbf{If } |f|<n \textbf{ then:}\\
&\quad \textbf{return } \texttt{false}\\
&\textbf{return } \{e=(p_{i},d_{j})\in E:f(e)=1\}
\end{align*}$$

The conservation constraint ensures that no person is assigned to more than one dining hall. Each person vertex has only one incoming edge. This edge has capacity one. Therefore, it can only have a flow of 1 on one outgoing edge. 

The conservation constraint ensures that no dining hall is over capacity. Each dining hall $h$ has only one outgoing edge. This edge has capacity $C_{j}$. Each person assigned to dining hall $j$ is an incoming edge with flow 1. Since at most $C_{j}$ flow leaves vertex $d_{j}$, at most $C_{j}$ people are assigned to it.

Suppose there is a feasible assignment. I will construct a valid flow on $G$ with size $n$. For each edge $e=(s,p_{i})$, let $f(e)=1$. If person $p_{i}$ is matched to dining hall $d_{j}$, let $f((p_{i},d_{j}))=1$. This ensures that the capacity constraint is satisfied on $p_{1},\ldots,p_{n}$, since every person has a matching by assumption. Since at most $C_{j}$ people are assigned to dining hall $j$ by the matching, there is at most $C_{j}$ flow on edges into $d_{j}$. So, we may complete a valid flow on $G$ by letting $$f((d_{j},t))=\sum_{e \text{ into }d_{j}}f(e)$$Since the existence of a feasible assignment implies the existence of a valid flow on $G$ with size $n$, the algorithm will return a valid matching whenever one exists.


>[!note] 3

Source $s$ with demand $-k$. Connect $s$ to each person $i$ with edge $e=(s,i)$. Let $c(e)=7$,  $l(e)=5$, and $d(i)=0$. Connect each person $i$ to each job $j\in L_{i}$ with edge $e=(i,j)$. Let $c(e)=1,l(e)=0$, and $d(i)=0$. Connect each job $j$ to the sink $t$ with edge $e=(j,t)$. Let $c(e)=1,l(e)=0$, and $d(t)=k$. 

$$\begin{align*}
&\textbf{Algorithm } \text{Workchart Wizardry}\\
&\textbf{Input: } \text{Jobs }j_{k}, \text{ People }p_{i}, \text{ Lists }L_{i}\\
&\text{Construct a graph }G=(V,E)\\
&\text{Let }V=\{s,t,p_{1},\ldots,p_{n},j_{1},\ldots,j_{m}\},E=\emptyset\\
&\textbf{If } 5\cdot n>m \textbf{ then:}\\
&\quad \textbf{return } \texttt{false}\\
&d(t)=-d(s)=\max\{k,5n\}\\
&\textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad d(p_{i})=0\\
&\quad \text{Add an edge }e=(s,p_{i})\text{ to }E\\
&\quad c(e)=7,l(e)=5\\
&\quad \textbf{For } j\in L_{i} \textbf{ do:}\\
&\quad \quad \text{Add and edge }e=(p_{i},j_{j})\text{ to }E\\
&\quad \quad c(e)=1,l(e)=0\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\textbf{For } 1\le j\le m \textbf{ do:}\\
&\quad d(j_{j})=0\\
&\quad \text{Add an edge }e=(d_{j},t)\text{ to }E\\
&\quad c(e)=1,l(e)=0\\
&\textbf{end for}\\
&\text{Let }s=\texttt{LowerBoundCirculation}(G,c,l,d)\\
&\textbf{return } s\ne \texttt{null}\\
\end{align*}$$

This decision algorithm checks if it is possible to assign $l$ jobs and satisfy the constraints. This is equivalent to the problem is it possible to assign some number $k\le l\le m$ jobs. 

The job assignments are represented by edges between people and job vertices with circulation 1. A job may only have one person assigned to it, since it has only one outgoing edge, and this edge has capacity one. The capacities and lower bounds on the incoming edge to each person ensure that a valid circulation assigns each person to 5-7 jobs; since the demands on each person are 0, the incoming 5-7 circulation must go out on 5-7 edges. Since the demand on $s$ is $-k$, a valid circulation must send $k$ total circulation to the people, and thus $k$ total jobs must be assigned. 