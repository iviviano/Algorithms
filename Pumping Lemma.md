---
mathLink: pumping lemma
---
>[!thm]
>If $A$ is a [[Regular Language]] [[Language]], then there is a number $p$ where if $s\in A$ with the [[Length]] of $s$ at least $p$, then $s$ may be written as $s=xyz$ with 
>1. for each $i≥0$, $xy^{i}z\in A$
>2. $|y|>0$
>3. $|xy|≤p$

>[!thm]
>If $A$ is a [[Regular Language]] [[Language]], then $A$ is [[Pumpable]].

>[!proof]

Let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]] with $L(M)=A$ and set $p=|Q|$.

If $A$ contains no strings of length at least $p$, we are done.

Otherwise, let $w$ be a string in $A$ of [[Length]] $n≥p$. Write $w_{1}\cdots w_{n}$ where each $w_{i}\in \Sigma$

Let $r_{0},r_{1},\ldots,r_{n}$ be the [[Accept]]ing computation of $M$ on $w$

By the [[Pigeonhole Principle]], pick two states $r_{j}=r_k$ with $j<k$. 