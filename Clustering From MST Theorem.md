---
mathLink: clustering from MST theorem
---
>[!thm]
>The components $C_{1},\ldots,C_{k}$ formed by deleting the $k-1$ most expensive edges from a [[Minimum Spanning Tree]] make a $k$-clustering of maximum [[Spacing]].

>[!proof]
Let $d^{*}$ be the [[Spacing]] of this $k$-[[Clustering]]. Then, $d^{*}$ is the weight of the $k-1$st most expensive edge in the [[Minimum Spanning Tree]]. Consider a different [[Clustering]] $C_{1}',\ldots,C_{k}'$. Then there are points $p_{i},p_{j}\in C_{r}$ with $p_{i}\notin C_{l}\lor p_{j}\notin C_{l}$ for all $l$. Clearly, $d(p_{i},p_{j})≤d^{*}$ as they are in a cluster. So, the [[Spacing]] of the other clustering is not greater than $d^{*}$.
