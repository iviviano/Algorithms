---
mathLink: generalized nondeterministic finite automaton
---
>[!def]
>A *generalized nondeterministic finite automaton* is a $5$-[[Tuple]], $(Q,\Sigma,\delta,q_{start},q_{accept})$, where
>1. $Q$ is the finite [[Set]] of [[States]]
>2. $\Sigma$ is the finite [[Alphabet]]
>3. $\delta:(Q-\{q_{accept}\})\times(Q-\{q_{start}\})\rightarrow \mathcal{R}$ is the [[Transition Function]]
>4. $q_{start}$ is the [[Start State]]
>5. $q_{accept}$ is the [[Accept]] [[States]]

>[!note] 
>- $\mathcal{R}$ is the [[Collection]] of all [[Regular Expression]]s over the [[Alphabet]] $\Sigma$. 
>- The [[Domain]] of $q$ is chosen because no arrows come from $q_{accept}$ or going to $q_{start}$

