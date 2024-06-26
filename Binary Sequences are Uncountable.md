---
mathLink: binary sequences are uncountable
---
>[!thm]
The [[Set]] $S$ of [[Sequence]]s over $\{0,1\}$ is uncountable.

>[!proof]
Assume $S$ is countable and let $f:\mathbb{N}\rightarrow S$ be [[Bijective]]. Denote the $i$-th element of $f(n)$ by $f(n)_{i}$. We construct: $b$ such that $$b_{i}=\begin{cases} 
0 & \text{if the }i \text{'th element of }f(i)\text{ is }1\\
1 & \text{if the }i \text{'th element of }f(i)\text{ is }0
\end{cases}$$
We have $b\in S$ but for all $i$, $$f(i)_{i}≠b_{i}\implies f(i)\ne b$$contradicting that $f$ is [[Surjective]].