---
mathLink: context-free language
---
>[!def]
>The [[Collection]] of [[Language]]s associated with [[Context-Free Grammar]]s are called the *context-free languages*.

>[!note]
>Every [[Regular Language]] [[Language]] is a [[Context-Free Languages]]

>[!proof]

Use structural induction on [[Regular Expression]]s: Three base cases: $$\begin{align*}
\varnothing: S &\rightarrow S\\
\varepsilon: S &\rightarrow \varepsilon\\
\forall t\in \Sigma: S&\rightarrow t\\
\end{align*}$$
Inductive 