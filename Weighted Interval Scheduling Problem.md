

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

