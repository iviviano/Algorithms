>[!note] 1
(a) $$\Sigma \Sigma \Sigma\ |\ \Sigma \Sigma\ |\ \Sigma\ |\ \varepsilon$$
(b) $$\Sigma^{+}$$
(c) $$\Sigma \texttt{b} \Sigma(\Sigma^{3})^{*}$$
(d) $$\texttt{a}^{*}(\texttt{b}\texttt{a}\texttt{a}^{+})^{*}$$
(e) $$\texttt{a}^{*}\texttt{b}^{*}$$

>[!2]

![[Long image 2024-03-11 15.22.04.jpg]]

>[!3]
Note that for all [[Language]]s $A,B\subseteq \Sigma^{*}$,
$$A-B= A\cap(\Sigma^{*}-B)$$where $\Sigma^{*}-B$ is the [[Compliment]] of $B$. So,
>$$\begin{align*}
A\ \triangle\ B&:= (A-B)\cup(B-A)\\
&= (A\cap(\Sigma^{*}-B))\cup(B\cap (\Sigma^{*}-A))
\end{align*}$$
Since $A$ and $B$ are [[Regular Language]] [[Language]]s, and the class of [[Regular Language]] [[Language]]s is [[Closed Under an Operation]] under [[Intersection]], [[Union]], and [[Compliment]], the symmetric difference is regular.


>[!4]
>$$\begin{align*}
S &\rightarrow AB\ |\ CD\\
A&\rightarrow \texttt{a}A \texttt{b}\ |\ \varepsilon\\
B&\rightarrow \texttt{c}B\ |\ \varepsilon\\
C&\rightarrow \texttt{a}C\ |\ \varepsilon\\
D&\rightarrow \texttt{b}D \texttt{c}\ |\ \varepsilon
\end{align*}$$

>[!5]
The [[Context-Free Grammar]] from (4) is [[Ambiguous Grammar]]. Here are two derivations of $\varepsilon$:
$$S\implies AB\implies \varepsilon B\implies \varepsilon \varepsilon=\varepsilon$$$$S\implies CD\implies \varepsilon B\implies \varepsilon \varepsilon=\varepsilon$$
