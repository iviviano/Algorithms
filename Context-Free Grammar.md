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
[[Derive]]: $$S\implies AB\implies \varepsilon B\implies \varepsilon\varepsilon$$
$$A\im$$