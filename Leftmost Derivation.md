---
mathLink: leftmost derivation
---
>[!def]
>A [[Derive]]ation of a [[String]] $w$ in a [[Context-Free Grammar]] $G$ is a *leftmost* derivation if at every step the leftmost remaining [[Variable]] is the one replaced.

Example: 
$$\begin{align*}
S&\rightarrow ST|\texttt{a}T  \texttt{a}\\
T&\rightarrow S|\texttt{a}T \texttt{a}|b
\end{align*}$$
Leftmost Derivation:
$$S\implies ST\implies \texttt{a}T \texttt{a}T\implies\texttt{aa}T \texttt{aa}T\implies \texttt{aabaa}T\implies \texttt{aabaaa}T \texttt{a}\implies \texttt{aabaaaba}$$
of the string `aabaaaba`
