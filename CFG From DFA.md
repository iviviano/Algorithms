---
mathLink: CFG from DFA procedure
---
>[!prop]
>Let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]]. The following procedure generates a [[Context-Free Grammar]] $G$ whose [[Language of a Grammar]] is [[Equivalent Machines]] to $M$. 
>1. Make a [[Variable]] $R_{i}$ for each [[States]] $q_{i}\in Q$.
>2. Add the [[Substitution Rule]] $R_{i}\rightarrow a R_{j}$ to the [[Context-Free Grammar]] if $\delta(q_{i},a)=q_{j}$ is a transition in the [[Deterministic Finite Automaton]]
>3. Add the [[Substitution Rule]] $R_{i}\rightarrow \epsilon$ if $q_i$ is an [[Accept]]ed [[States]]. 
>4. Make $R_0$ the [[Start Variable]] of $G$
