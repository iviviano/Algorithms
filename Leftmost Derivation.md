---
mathLink: leftmost derivation
---
>[!def]
>A [[Derive]]ation of a [[String]] $w$ in a [[Context-Free Grammar]] $G$ is a *leftmost* derivation if at every step the leftmost remaining [[Variable]] is the one replaced.

Example: 
$$\begin{align*}
S&\rightarrow ST|\texttt{a}T  \texttt{a}\\
T&\rightarrow S|\texttt{a}
\end{align*}$$