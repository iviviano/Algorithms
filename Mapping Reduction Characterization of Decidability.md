---
mathLink: mapping reducibility characterization of decidability
---
>[!thm]
>If $A\le_{m}B$ and $B$ is [[Turing-Decidable]], then $A$ is [[Turing-Decidable]].

>[!proof]
Let $R$ be a [[Decider]] for $B$ and let $f:\Sigma^{*}\rightarrow \Sigma^{*}$ be the [[Mapping Reduction]]. 
The following [[Turing Machine]] [[Decide]]s $A$:
On input $w$:
>1. Compute $f(w)$
>2. Run $R$ on $f(w)$ and if $R$ [[Accept]]s, then [[Accept]], else reject.

>[!prop] Corollary
>If $A\le_{m}B$ and $A$ is [[Undecidable]], then $B$ is [[Undecidable]].

