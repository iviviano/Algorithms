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
