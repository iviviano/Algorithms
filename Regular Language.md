---
mathLink: regular
---
>[!def]
>A [[Language]] is a *regular language* if some [[Deterministic Finite Automaton]] [[Recognize]]s it.

>[!prop]
>The [[Language]] $$A=\{\texttt{0}^{n}\texttt{1}^{n}|n≥0\}$$is not regular

>[!proof]
Suppose $A$ is [[Regular Language]]. Let $p$ be the [[Pumping Length]] of $A$. Consider $$w=0^{p}1^{p}$$Let $xyz=w$ such that $|xy|≤p$ and $|y|>0$. We have $$\begin{align*}
x&= 0^{l}\\
y&= 0^{k}\\
z&= 0^{p-l-k}1^{p}
\end{align*}$$We have $k>0$, since $|y|>0$. Consider the [[String]] $$xy^{2}z=0^{l}0^{2k}0^{p-l-k}1^{p}=0^{p+k}1^{p}$$But since $k>0$, $p+k\ne p$. So, $$xy^{2}z\notin A$$This contradicts the [[Pumping Lemma]], so $A$ is not [[Regular Language]].

>[!prop]
>The [[Language]] of [[Palindrome]]s $$B=\{w|w\in\{0,1\}^{*}\text{ and }w=w^\mathcal{R}\}$$

>[!prop]

Suppose $B$ is [[Regular Language]]. let $p$ be the [[Pumping Length]] of $A$. Consider $$w=0^{p}10^{p}$$Let $xyz=w$ such that $|xy|≤p$ and $|y|>0$. We have $$\begin{align*}
x&= 0^{m}\\
y&= 0^{l}\\
z&= 0^{p-l-m}10^{p}
\end{align*}$$Since $|y|>0$, $l>$Then, $$xy^{0}z= 0^{m}0^{p-l-m}10^{p}=$$