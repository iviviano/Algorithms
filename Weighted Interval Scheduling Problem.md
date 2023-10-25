Input: 
- $n$ jobs
- job $i$ has 
	- start $s_{i}$
	- end $e_{i}$
	- value $v_{i}$

Output:
- selection, $S$, of jobs that don't overlap

Optimality:
- Maximize $\sum_{i\in S} v_{i}$ of solution

>[!alg]
>$$\begin{align}
&\textbf{Algorithm } \text{Brute Force Solution}\\
&\textbf{Input: } \text{Set }J \text{ of jobs}\\
&\textbf{Output: } \text{Subset of }J\\
&\textbf{If } J==\emptyset \textbf{ then:}\\
&\quad \textbf{return } \emptyset\\
&\text{Let } j\in J\\
&\text{Let }J'\text{ be the subset of }J \text{ compatible with }j\\
& \text{Let } J_{1}=\{j\}\cup\text{OPT}(J')\\
&\text{Let } J_{2}=\text{OPT}(J-\{j\})\\
&\text{Let OPT}(J)=\max\{J_{1},J_{2}\}
\end{align}$$

Worst case for brute force algorithm occurs when all jobs are compatible. In this case, there are about $2^{n}$ calls to $\text{OPT}$.

>[!alg]
>$$\begin{align}
&\textbf{Algorithm } \text{Dynamic Programming Solution}\\
&\textbf{Input: } \text{Sorted set } J \text{ of } n \text{ jobs by endtime}\\
&\quad \text{And prev}(j)\text{ for each }j\in J \text{ to be the last job compatible with }j \text{ with prev}(j)<j\\
&\textbf{Output: } \text{Subset of }J\\
&\textbf{If } J==\emptyset \textbf{ then:}\\
&\quad \textbf{return } \emptyset\\
&\text{Let }J_{1}=\{j_{n}\}\cup \text{OPT}(\text{prev}(j))\\
&\text{Let }J_{2}=\text{OPT}(J-\{j_{n}\})\\
&\textbf{If } \sum_{j\in J_{1}}v_{j}\gt\sum_{j\in J_{2}}v_{j} \textbf{ then:}\\
&\quad \text{OPT}(J)=J_{1}\\
&\quad \textbf{return } J_{1}\\
&\textbf{Else:}\\
&\quad \text{OPT}(J)=J_{2}\\
&\quad \textbf{return } J_{2}\\
\end{align}$$

>[!note]
>In this implementation, $\text{OPT}$ checks if a value has been defined. If not, it calls the function on it.

[[therefore]] $\text{OPT}$ is called at most $n$ times.

This algorithm is $O(n\log n)$. Sorting $J$ is $O(\log n)$. The recursive part is $O(n)$. Computing $\text{prev}$ takes $O(n\log n)$. Use binary search on finish time with start time of each job.