---
mathLink: accept
---
>[!def]
>Let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]] and $w=w_{1}\cdots w_{n}$ be a [[String]] over the [[Alphabet]] $\Sigma$. Then, $M$ *accepts* $w$ if we can pick a [[Sequence]] of [[States]] $r_{0},\ldots,r_{n}$ in $Q$ such that 
>1. $r_{0}=q_{0}$ 
>2. $r_{i+1}=\delta(r_{i},w_{i+1})$ for $i=0,\ldots,n-1$
>3. $r_{n}\in F$


>[!def]
>Let $N=(Q,\Sigma,\delta,q_{0},F)$ be a [[Nondeterministic Finite Automaton]] and $w=w_{1}\cdots w_{n}$ be a [[String]] over the [[Alphabet]] $\Sigma_\varepsilon$. Then, $M$ *accepts* $w$ if we can pick a [[Sequence]] of [[States]] $r_{0},\ldots,r_{n}$ in $Q$ such that 
>1. $r_{0}=q_{0}$ 
>2. $r_{i+1}\in\delta(r_{i},w_{i+1})$ for $i=0,\ldots,n-1$
>3. $r_{n}\in F$


>[!def]
Let $G=(Q, \Sigma,\delta,q_{start},q_{accept})$ be a [[Generalized Nondeterministic Finite Automaton]] and let $w$ be a [[String]] in $\Sigma_\varepsilon^{*}$. Then, $G$ *accepts* $w$ if $w=w_{1},\ldots,w_{k}$, and a [[Sequence]] of [[States]] $q_{0},\ldots,q_{k}$ exists such that 
>1. $q_{0}=q_{start}$
>2. $q_{k}=q_{accept}$
>3. for each $i$, we have $w_{i}\in L(\delta(q_{i-1},q_{i}))$


>[!def]
>Let $M=(Q,\Sigma,\Gamma,\delta,q_{0},F)$ be a [[Pushdown Automaton]] and let $w$ be a [[String]] in $\Sigma$. Then, $M$ *accepts* $w$ if $w=w_{1}\cdots w_{n}$, where each $w_{i}\in \Sigma_\epsilon$, a [[Sequence]] of [[States]] $r_{0},\cdots,r_{n}\in Q$, and [[String]]s $s_{0},\ldots,s_{n}\in \Gamma^{*}$ exist such that
>1. $r_{0}=q_{0}$ and $s_{0}=\epsilon$. 
>2. For $i=0,\ldots,n-1$, we have $(r_{i+1},b)\in \delta(r_{i},w_{i+1},a)$, where $s_{i}=at$ and $s_{i+1}=bt$ for some $a,b\in \Gamma_\epsilon$ and $t\in \Gamma^*$
>3. $r_{m}\in F$

>[!note]
>1. Makes sure $M$ starts out properly in the [[Start State]] with empty [[Stack]]
>2. $M$ moves properly according to the state, stack, and next input [[Symbol]]
>3. Accept state occurs at the input end


>[!def]
>Let $M=(Q,\Sigma,\Gamma,\delta,q_{0},q_{accept},q_{reject})$ be a [[Turing Machine]] and let $w$ be an input [[String]]. Then, $M$ *accepts* $w$ if a [[Sequence]] of [[Configuration]]s $C_{1},\ldots,C_n$ exists such that 
>1. $C_{1}$ is the [[Start Configuration]] of $M$ on $w$
>2. each $C_{i}$ [[Yield]]s $C_{i+1}$
>3. $C_n$ is an [[Accepting Configuration]]
