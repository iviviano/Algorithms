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



Attach the source to each person with capacity 1. Attach every dining hall $j$ to the sink with capacity $C_{j}$. Attach each person $i$ to each dining hall in $S_i$ with capacity 1.

Compute [[Max Flow Problem]] on $G$. Return `false` if $|f|<n$. 


>[!note] 3

Source $s$ with demand $-k$. Connect $s$ to each person $i$ with edge $e=(s,i)$. Let $c(e)=7$,  $l(e)=5$, and $d(i)=0$. Connect each person $i$ to each job $j\in L_{i}$ with edge $e=(i,j)$. Let $c(e)=1,l(e)=0$, and $d(i)=0$. Connect each job $j$ to the sink $t$ with edge $e=(j,t)$. Let $c(e)=1,l(e)=0$, and $d(t)=k$. 