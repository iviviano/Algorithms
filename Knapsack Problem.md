---
mathLink: knapsack problem
---
>[!def]
Maximize the value of a subset sum while meeting a weight requirement.

Input:
- $n$ objects
- weights $w_{i}$ (integers)
- values $v_{i}$ (integers)
- weight maximum $C$
Goal: pick subset $S$ of $[n]$ such that $$\sum_{i\in S}w_{i}\le C$$and $$\sum_{i\in S}v_{i}$$is maximized.

Step 1: Let $\text{OPT }(i,D)$ be the maximum value of a subset of $[i]$ weighing less than $D$

Step 2: $$\texttt{OPT}(i,D)=\begin{cases} 
&\texttt{OPT}(i-1,D)\text{ if }w_{i}>D\\
&\max\{\texttt{OPT}(i-1,D-w_{i})+v_{i},\texttt{OPT}(i-1,D)\}\text{ otherwise}\end{cases}$$
Step 3: Proof of 2

Step 4: Base Cases:
$$\texttt{OPT}(0,D)=0$ for all $D\le C$$
Step 5: find $\texttt{OPT}(n,C)$

Step 6: $$\begin{align}
&\text{Let }memo \text{ be a }2D \text{ array of integers with length }C \text{ and width }n\\
&memo[1:C]=0\\
&\textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad \textbf{For } 1\le D\le C \textbf{ do:}\\
&\quad \quad \textbf{If } w_{i}>D \textbf{ then:}\\
&\quad \quad \quad memo[D][i]=memo[D][i-1]\\
&\quad \quad \textbf{Else:}\\
&\quad \quad \quad memo[D][i]=\max\{memo[D-w_{i}][i-1]+v_{i},memo[D][i-1]\}\\
&\textbf{end for}\\
&\textbf{return } memo[C][n]\\
\end{align}$$
Step 7:
This has runtime $O(n^{2})$
