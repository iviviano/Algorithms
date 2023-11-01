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

Step 4:

