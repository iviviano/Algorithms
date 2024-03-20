---
mathLink: a language is context free $\iff$ some pushdown automaton recognizes it
---
>[!thm]
>A [[Language]] is a [[Context-Free Languages]] [[iff]] some [[Pushdown Automaton]] [[Recognize]]s it.

>[!prop] Corollary
>Every [[Regular Language]] [[Language]] is a [[Context-Free Languages]]

>[!proof]

($\implies$) Let $A$ be a [[Context-Free Languages]] recognized by the [[Context-Free Grammar]] $G=(V,\Sigma,R,S)$. 





>[!example]

Consider the [[Language]] $A=\{w|w\in\{\texttt{a,b}\}^{*}\text{ and }w \text{ is not a palindrome}\}$. [[Context-Free Grammar]] recognizing $A$: $$\begin{align*}
S&\rightarrow \texttt{a}T \texttt{b}\ |\ \texttt{b}T \texttt{a}\ |\ \texttt{a}S \texttt{a}\ |\ \texttt{b}S \texttt{b}\\
T&\rightarrow \texttt{a}T \ |\ \texttt{b}T\ |\ \texttt{b}\ |\ \varepsilon
\end{align*}$$
[[Leftmost Derivation]] of $\texttt{abaaa}$: $$S\implies \texttt{a}S \texttt{a}\implies \texttt{ab}T \texttt{aa}\implies \texttt{aba}T \texttt{aa}\implies \texttt{abaaa}$$
We want to start by pushing $S$ on the stack, then performing the derivation step so that $\texttt{abaaa}$ ends on the stack, and then match the input.

Issues:
1. First step involves popping one symbol and pushing 3
2. We can only replace symbols at the top of the stack