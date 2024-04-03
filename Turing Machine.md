---
mathLink: Turing machine
---
>[!def]
>A *Turing machine* is a $7$-[[Tuple]], $(Q,\Sigma,\Gamma,\delta,q_{0},q_{accept},q_{reject})$, where $Q,\Sigma,\Gamma$ are finite [[Set]]s and
>1. $Q$ is the [[Set]] of [[States]]
>2. $\Sigma$ is the input [[Alphabet]] not containing the [[Blank Symbol]]
>3. $\Gamma$ is the tape [[Alphabet]], where $\textvisiblespace\in \Gamma$ and $\Sigma\subseteq \Gamma$
>4. $\delta:Q\times \Gamma\rightarrow Q\times \Gamma\times\{L,R\}$ is the [[Transition Function]]
>5. $q_{0}\in Q$ is the [[Start State]]
>6. $q_{accept}\in Q$ is the [[Accept]] [[States]]
>7. $q_{reject}\in Q$ is the [[Reject State]], where $q_{reject}≠q_{accept}$

$\texttt{\visiblespace}$
