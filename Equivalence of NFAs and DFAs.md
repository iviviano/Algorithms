---
mathLink: equivalence of NFAs and DFAs
---
>[!thm]
>Every [[Nondeterministic Finite Automaton]] has an [[Equivalent Machines]] [[Deterministic Finite Automaton]].

>[!prop] Corollary
>A [[Language]] is [[Regular Language]] [[iff]] some [[Nondeterministic Finite Automaton]] [[Recognize]]s it.

>[!proof]

Given an [[Nondeterministic Finite Automaton]] $N=(Q,\Sigma,\delta,q_{0},F)$, we can convert $N$ to a [[Deterministic Finite Automaton]] $M=(Q',\Sigma,\delta',q_{0}',F')$: 
- $Q'=\mathcal{P}(Q)$
- $q_{0}'=\{q_{0}\}$
- $\delta'(S,s)=\{q:q\in \delta'(S,s)\}$
- $F'=\{S\subseteq Q: S\cap F\ne \emptyset\}$
