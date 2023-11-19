>[!note] 1


>[!note] 2

(a) False. Consider the following simple flow network where the sum violates the capacity condition: 


(b) False. The following simple example violates the conservation condition:


(c) False. Consider the following graph with capacities shown in blue. The minimum cut has value 6. However, after adding 1 to all capacities, a different minimum cut has value 8.



>[!note] 3


$$\begin{align*}
&\textbf{Algorithm } \text{Nuts About Flow}\\
&\textbf{Input: } \text{Graph }G=(V,E)\text{, capacities }c,\text{ flow }f\\
&\textbf{Output: } \text{Adjusted flow on }G \text{ to meet capacity}\\
&\text{Perform a breadth-first search}\\
&\textbf{If } \text{there are no edges over capacity} \textbf{ then:}\\
&\quad \textbf{return } f\\
&\text{Let }P \text{ be a path from }s \rightarrow t \text{ with some edge }e\in P:c(e)<f(e)\\
&\text{Form a new flow }f'\\
&\textbf{For } e\in E \textbf{ do:}\\
&\quad \textbf{If } e\in P \textbf{ then:}\\
&\quad \quad f'(e)=f(e)-1\\
&\quad \textbf{Else:}\\
&\quad \quad f'(e)=f(e)\\
&\quad \textbf{end if}\\
&\textbf{end for}\\
&\text{Let }G_{f'} \text{ be the residual graph for the flow}f'\\
&\textbf{If } \text{there is a path }P \text{ from } s \rightarrow t \text{ in }G_{f'}\textbf{ then:}\\
&\quad \text{Augment }f' \text{along }P\\
&\textbf{return } f'
\end{align*}$$
>[!proof]

By definition, if there are no edges over capacity, then $f$ is still a valid flow. If there is an edge over capacity, we can pick a path $P$ from $s$ to $t$ with the flow on some edge in $P$ exceeding capacity. 

Claim: the flow $f'$ is a flow. 
We must show that $f'$ satisfies the capacity constraint and the conservation constraint. Let $e\in E$. Then, $f(e)≤c(e)+1$, since $f$ was a flow before the squirrels came. If $f(e)>c(e)$, then $e\in P$, since there is a unique edge such that this is true, and $P$ contains that edge. Since $f'(e)=f(e)-1≤c(e)+1-1=c(e)$, $f'(e)\le c(e)$. Of course, if $f(e)\le c(e)$, then $f'(e)\le f(e)\le c(e)$. Therefore, $f'$ satisfies the capacity constraint. Let $v\in E-\{s,t\}$ be given. Suppose no edge to $v$ is in $P$. Then, no edge out of $P$ is is in $P$. In this case, the flow $f'$ through all edges into or out of $P$ is the same as the flow $f$. So, the conservation constraint holds for $v$, since $f$ is a flow. Otherwise, there is an edge to $v$ in $P$. Since $P$ is a path to $t$, there is only one edge to $v$ in $P$ and exactly one edge out of $v$ in $P$. Since the $f$ is a flow and $f'$ is one less than $f$ on each of these edges, the conservation constraint holds for $v$. So, $f'$ is a flow. 

Since $f'$ is a flow, the feasibility of FF shows that this algorithm returns a flow.

The optimality of $f'$ similarly follows from the optimality of FF. If there is no path from $s$ to $t$ in $G_{f'}$, then we cannot improve from $f'$ (NEED TO EXPLAIN THIS). Otherwise, augmenting $f'$ adds at least one. Since the value of $f'$ is lower than the value of $f$ by one and $f$ is a max flow, the augmented $f'$ is also a max flow.
