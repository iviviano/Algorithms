---
mathLink: class of regular languages closed under union
---
>[!thm]
>The class of [[Regular Language]] [[Language]]s is [[Closed Under an Operation]] under the [[Language Union]].

>[!proof] Proof with nondeterminism
Let $A_{1},A_{2}$ be [[Language]]s. Let $M_{1}=(Q_1,\Sigma_{1},\delta_{1},q_{0}^{1},F_{1})$ be an [[Deterministic Finite Automaton]] with $L(M_{1})=A_1$. Let $M_{2}=(Q_2,\Sigma_{2},\delta_{2},q_{0}^{2},F_{2})$ be an [[Deterministic Finite Automaton]] with $L(M_{2})=A_2$. 
>
Let $Q=Q_{1}\cup Q_{2}\cup\{q_0\}$ for new states $q_{0}\notin Q_{1}\cup Q_{2}$. Let $\Sigma=\Sigma_{1}\cup \Sigma_{2}$. Let $F=F_{1}\cup F_{2}$. Let $\delta:Q\times\Sigma_{\epsilon}\rightarrow\mathcal{P}(Q)$ be defined by $$\delta(q,s)=\begin{cases}  \emptyset & \text{if }s=\varepsilon\text{ and }q≠q_{0}\\
\{q_{0}^{1},q_{0}^{2}\} & \text{if }s=\varepsilon
\text{ and }q=q_{0} \\
\emptyset & \text{if }s≠\varepsilon \text{ and }q=q_{0} \\
\{\delta_{i}(q,s)\} & \text{if }q\in Q_{i}
\end{cases}$$ Then, the [[Nondeterministic Finite Automaton]] $M=(Q,\Sigma,\delta,q_{0},F)$ [[Recognize]]s $A=A_{1}\cup A_{2}$. Let $w=w_{1},\ldots,w_{n}\in A_1$. Let $r_{0},\ldots,r_{n}$ be the [[Accept]]ance [[Sequence]] of $w$ by $M_1$. Then, $q_{0},r_{0},\ldots,r_{n}$ is an [[Accept]]ance [[Sequence]] of $w$ by $M$:
>1. $q_{0}=q_{0}$ 
>2. For each $r_{i}$, $\delta_{1}(r_{i},w_{i})=r_{i+1}\in Q_1$, so $\delta(r_{i},w_{i})=\{\delta_{1}(r_{i},w_{i})\}=\{r_{i+1}\}\ni r_i+1$.
>3. $r_{n}\in F_{1}\subseteq F$
Let $w\notin A$. (FINISH)
>
So, $A$ is a [[Regular Language]] [[Language]] by the [[Equivalence of NFAs and DFAs]]. 



