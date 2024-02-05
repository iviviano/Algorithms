---
mathLink: accept
---
>[!def]
>Let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]] and $w=w_{1}\cdots w_{n}$ be a [[String]] over the [[Alphabet]] $\Sigma$. Then, $M$ *accepts* $w$ if we can pick a [[Sequence]] of [[States]] $r_{0},\ldots,r_{n}$ in $Q$ such that 
>1. $r_{0}=q_{0}$ 
>2. $r_{i+1}=\delta(r_{i},w_{i+1})$ for $i=0,\ldots,n-1$
>3. $r_{n}\in F$

>[!def]
>Let $N=(Q,\Sigma,\delta,q_{0},F)$ be a [[Nondeterministic Finite Automaton]] and $w=w_{1}\cdots w_{n}$ be a [[String]] over the [[Alphabet]] $\Sigma$. Then, $M$ *accepts* $w$ if we can pick a [[Sequence]] of [[States]] $r_{0},\ldots,r_{n}$ in $Q$ such that 
>1. $r_{0}=q_{0}$ 
>2. $r_{i+1}\in\delta(r_{i},w_{i+1})$ for $i=0,\ldots,n-1$
>3. $r_{n}\in F$

>[!def]
Let $G=(Q, \Sigma,\delta,q_{start},q_{accept})$ be a [[Generalized Nondeterministic Finite Automaton]] and let $w$ be a [[String]] in $\Sigma^{*}$. Then, $G$ *accepts* $w$ if $w=w_{1},\ldots,w_{k}$, and a [[Sequence]] of [[States]] $q_{0},\ldots,q_{k}$ exists such that 
>1. $q_{0}=q_{start}$
>2. $q_{k}=q_{accept}$
>3. for each $i$, we have $w_{i}\in L(\delta(q_{i-1},q_{i}))$
