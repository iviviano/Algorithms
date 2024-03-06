---
mathLink: context-free grammar
---
>[!def]
>A *context-free grammar* is a $4$-[[Tuple]] $(V,\Sigma,R,S)$ where 
>1. $V$ is a finite [[Set]] of [[Variable]]s
>2. $\Sigma$ is a finite [[Set]] [[Disjoint]] from $V$ called the [[Terminal]]s
>3. $R$ is a finite [[Set]] of [[Substitution Rule]]s
>4. $S\in V$ is the [[Start Variable]]


Example: 
$$\begin{align*}
S &\rightarrow AB\\
A &\rightarrow \texttt{a}A|\varepsilon\\
B &\rightarrow \texttt{b}B|\varepsilon
\end{align*}$$
[[Derive]]: $$S\implies AB\implies \varepsilon B\implies \varepsilon\varepsilon=\varepsilon$$
$$A\implies AB\implies \texttt{a}AB\implies a \varepsilon B\implies \texttt{aab}B\implies\texttt{aab}\varepsilon=\texttt{aab}$$

Properly nested parens: $\Sigma=\{(,),[,]\}$
$$\begin{align*}
S&\rightarrow P|B|SS|\varepsilon\\
P&\rightarrow(S)\\
B&\rightarrow[B]
\end{align*}$$
or
$$\begin{align*}
S&\rightarrow (S)\ |\ [B]\ |\ SS\ |\ \varepsilon
\end{align*}$$

Language $A=\Sigma^{*}$: $$\begin{align*}
S&\rightarrow \texttt{a}S|\texttt{b}S|\varepsilon
\end{align*}$$
Language $B=\{w|w \text{ contains at least three }\texttt{b}s\}$
$$\begin{align*}
S&\rightarrow NbNbNbN\\
N&\rightarrow aN|bN|\varepsilon
\end{align*}$$
Language $C=\{w|w \text{ starts and ends with different symbols }\}$
$$\begin{align*}
S&\rightarrow \texttt{a}N\texttt{b}|bNa\\
N&\rightarrow aN|bN|\varepsilon
\end{align*}$$
Language $D=\{w|\text{ the length of }w \text{ is odd and the nmiddle symbol is }\texttt{b}\}$:
$$\begin{align*}
S&\rightarrow
\end{align*}$$