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

Step 1: Let $\text{OPT }(i)$ be the maximum value of a subset of 