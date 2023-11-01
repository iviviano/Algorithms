---
mathLink: knapsack problem
---
>[!def]
Maximize the value of a subset sum while meeting a weight requirement.

Input:
- $n$ objects
- weights $w_{i}$
- values $v_{i}$
- weight maximum $C$. 
Goal: pick subset $S$ of $[n]$ such that $$\sum_{i\in S}w_{i}\le C$$and $$\sum_{i\in S}v_{i}$$is maximized.

Step 1: Let $\text{OPT }(j,D)$ be the maximum value of a subset of $[j]$ weighing less than $D$

Step 2: Recurrence: $$\text{OPT }(j)=\max\begin{cases}v_{j}+\text{OPT }(j-i)\text{ if }v_{j}+\text{OPT }(j-i)<C\\\text{for all }i\le j\\\text{and }\text{OPT }(j-1)\end{cases}$$
$$\text{OPT }(j)=\max\{\text{OPT }(j-1),v_{j}+\text{OPT }(prev(j))\}$$
