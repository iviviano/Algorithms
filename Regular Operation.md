---
mathLink: regular operation
---
>[!def]
>The *regular operations* are [[Compliment]], [[Language Union]], [[Language Concatenation]]e, and [[Star]].

>[!proof] Proof (compliment)
Let $A$ be a [[Regular Language]] [[Language]] and let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]] that [[Recognize]]s $A$. Let $$M'=(Q,\Sigma,\delta,q_{0},Q-F)$$Then, $M'$ is a [[Deterministic Finite Automaton]] that [[Recognize]]s $A^{c}$, so $A^{c}$ is [[Regular Language]].

>[!proof] Proof (union)

Let $A_1$ be a [[Deterministic Finite Automaton]] [[Recognize]]d by $M_{1}=(Q_{1},\Sigma_{1},\delta_{1},q_{1},F_{1})$. Let $A_1$ be a [[Deterministic Finite Automaton]] [[Recognize]]d by $M_{2}=(Q_{2},\Sigma_{2},\delta_{2},q_{2},F_{2})$.

Let $M=(Q,\Sigma,\delta:Q\times \Sigma,q,F)$ where $$\begin{align}Q&=Q_{1}\times Q_{2}\\
\Sigma&=\Sigma_{1}\cup\Sigma_{2}\\
\delta((q_{1},q_{2}),s)&=((\delta_{1}(q_{1},s),\delta_{2}(q_{2},s))\\
q&=(q_{1},q_{2})\\
F=\end{align}$$