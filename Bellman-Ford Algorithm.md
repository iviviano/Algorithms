>[!def]
>A [[Dynamic Programming Paradigm]] solution to the [[Shortest Paths Problem]]. The idea is to impose a measure of progress to parameterize the subproblems.

We will measure progress by the number of edges in the path.

1. Compute all possible shortest paths with $≤$ $1$ edge.
2. Do the same with $≤2$ edges
3. ...
4. If no negative [[Cycle]], can stop after computing all shortest paths with $≤n-1$ edges

Step 1: $\texttt{OPT}(v,i)$ is the length of the shortest path from $s$ to $v$ with at most $i$ edges.

Step 2: $$\texttt{OPT}(v,i)=\min\{\texttt{OPT}(v,i-1),\texttt{OPT}(u,i-1)+w(u,v):u \text{ is a neighbor of }v\}$$
Step 3: 

Step 4:
Base cases: $\texttt{OPT}(v,0)=\infty$ for all $v≠s$. $\texttt{OPT}(s,0)=0$.

Step 5: Goal is to find $$\texttt{OPT}(:n-1)$$

Step 6: $$\begin{align*}
&\text{Let }memo[n][n] \text{ be an array of integers}\\
&memo[0][0]=0\\
&memo[1:n-1][0]=\infty\\
&\textbf{For } 1\le i\le n-1 \textbf{ do:}\\
&\quad \textbf{For } 1\le v\le n \textbf{ do:}\\
&\quad \quad memo[i][v]=recurrence\\
&\textbf{return } memo[1:n-1][n-1]
\end{align*}$$
This is $O(n^{3})$. If there are $m$ [[edge]]s and $m<<n^{2}$, then the runtime is $O(mn)$. 

Finding negative cycles: 
- Run again: row $n$ of the memo table contains shortest path length using $≤i$ edges
- If no negative cycles, row $n$ is identical to $n-1$
- The paths with negative cycles are given by the columns for which row $n$ differs from $n-1$.

Adapted algorithm: $$\begin{align*}
&\text{Let }memo[n][n] \text{ be an array of integers}\\
&memo[0][0]=0\\
&memo[1:n-1][0]=\infty\\
&\textbf{For } 1\le i\le n-1 \textbf{ do:}\\
&\quad \textbf{For } 1\le v\le n \textbf{ do:}\\
&\quad \quad memo[i][v]=recurrence\\
&\textbf{For } 1\le v\le n \textbf{ do:} \\
&\quad \text{Let }d \text{ be the recurrence value for }i,n\\
&\quad \textbf{If } d≠memo[i][n-1] \textbf{ then:}\\
&\quad \quad memo[i][n]=\infty\\
&\textbf{return } memo[1:n-1][n-1]
\end{align*}$$