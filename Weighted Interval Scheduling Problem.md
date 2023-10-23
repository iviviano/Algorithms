

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

$$\begin{align}
&\textbf{Algorithm } \text{Brute Force Solution}\\
&\textbf{Input: } \text{Set }J \text{ of jobs}\\
&\textbf{Output: } \text{}\\
&\textbf{For } j\in J \textbf{ do:}\\
&\quad \textbf{If } j\in\text{OPT}(J) \textbf{ then:}\\
&\quad \quad \text{Let }J'\text{ be the subset of }J \text{ compatible with }j\\
&\quad \quad \textbf{return } \{j\}\cup\text{OPT}(J')\\
&\quad \textbf{Else:}\\
&\quad \quad \textbf{return } \text{OPT}(J-\{j\})
\end{align}$$
