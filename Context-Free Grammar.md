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

$$\begin{align*}
S&\rightarrow (S)|
\end{align*}$$