---
mathLink: regular operation
---
>[!def]
>The *regular operations* are [[Compliment]], [[Language Union]], [[Language Concatenation]]e, and [[Star]].

>[!note]
>Can use these to show a language is not regular: let $A$ be a non-[[Regular Language]] [[Language]]. If we do regular operations on $A$ and arrive at a non-regular language, we show that $A$ is not 

>[!proof] Proof (compliment)
Let $A$ be a [[Regular Language]] [[Language]] and let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]] that [[Recognize]]s $A$. Let $$M'=(Q,\Sigma,\delta,q_{0},Q-F)$$Then, $M'$ is a [[Deterministic Finite Automaton]] that [[Recognize]]s $A^{c}$, so $A^{c}$ is [[Regular Language]].

>[!proof] Proof (union)

Let $A_1$ be a [[Deterministic Finite Automaton]] [[Recognize]]d by $M_{1}=(Q_{1},\Sigma,\delta_{1},q_{1},F_{1})$. Let $A_1$ be a [[Deterministic Finite Automaton]] [[Recognize]]d by $M_{2}=(Q_{2},\Sigma,\delta_{2},q_{2},F_{2})$.

Let $M=(Q,\Sigma,\delta:Q\times \Sigma \rightarrow Q,q,F)$ where $$\begin{align}Q&=Q_{1}\times Q_{2}\\
\Sigma&=\Sigma_{1}\cup\Sigma_{2}\\
\delta((q_{1},q_{2}),s)&=((\delta_{1}(q_{1},s),\delta_{2}(q_{2},s))\\
q&=(q_{1},q_{2})\\
F&=F_{1}\times Q_{2}\cup Q_{1}\times F_{2}\end{align}$$
and $\delta(q,\epsilon)=\{q_{1},q_{2}\}$. Then, $M$ is a [[Nondeterministic Finite Automaton]] that [[Recognize]]s $A_{1}\cup A_2$. So by the [[Equivalence of NFAs and DFAs]], $A_{1}\cup A_{2}$ is [[Regular Language]].