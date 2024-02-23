---
mathLink: a language is regular $\iff$ some regular expression describes it
---
>[!thm]
>A [[Language]] is [[Regular Language]] [[iff]] some [[Regular Expression]] describes it.

>[!proof]



Removing states from an GNFA:
1. Select a state to remove $r$  other than the start or accept states $(r\in Q-\{q_{0},q_{a}\})$
2. For each $q,s\in Q-\{r\}$ we have $$\begin{align*}\\
R_{1}&= \delta(q_0,r)\\
R_{2}&= \delta(r,r)\\
R_{3}&= \delta(r,q_{a})\\
R_{4}&= \delta(q_{0},q_{a})
\end{align*}$$if any $R_i$ does not exist, it is $\emptyset$.
3. Remove the state $r$ from $Q$ and replace $R_4$ with $$R_{1}R_{2}^{*}R_{3}|R_{4}$$
>[!note]
>We also consider pairs $q,q$ of states.


