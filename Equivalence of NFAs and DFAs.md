---
mathLink: equivalence of NFAs and DFAs
---
>[!thm]
>Every [[Nondeterministic Finite Automaton]] has an [[Equivalent Machines]] [[Deterministic Finite Automaton]].

>[!prop] Corollary
>A [[Language]] is [[Regular Language]] [[iff]] some [[Nondeterministic Finite Automaton]] [[Recognize]]s it.

>[!proof]
Given an [[Nondeterministic Finite Automaton]] $N=(Q,\Sigma,\delta,q_{0},F)$, we can convert $N$ to a [[Deterministic Finite Automaton]] $M=(Q',\Sigma,\delta',q_{0}',F')$: 
>- $Q'=\mathcal{P}(Q)$
>- $q_{0}'=\{q_{0}\}$
>- $\delta'(R,a)=\{q\in Q:\delta(r,a)\text{ for some }r\in Q\}$ or $$\delta'(R,a)=\bigcup_{r\in R}\delta(r,a)$$
>- $F'=\{S\subseteq Q: S\cap F\ne \emptyset\}$
