---
mathLink: regular operation
---
>[!def]
>The *regular operations* are [[Compliment]], [[Language Union]], [[Language Concatenation]]e, and [[Star]].

>[!proof] Proof (compliment)

Let $A$ be a [[Regular Language]] [[Language]] and let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]] that [[Recognize]]s $A$. Let $$M'=(Q,\Sigma,\delta,q_{0},Q-F)$$Then, $M'$ [[Recognize]]s $A^{c}$. 

>[!proof] Proof (union)