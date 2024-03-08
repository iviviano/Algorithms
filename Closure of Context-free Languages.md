---
mathLink: closure of context-free languages
---
>[!thm]
>The class of [[Context-Free Languages]]s are [[Closed Under an Operation]] under the [[Regular Operation]]s [[Union]], [[Language Concatenation]]ion, and [[Star]].

>[!proof]

Union: 
Let $G_{1}=(V_{1},\Sigma,R_{1},S_{1})$ have the [[Language]] $A$ and $G_{2}=(V_{2},\Sigma,R_{2},S_{2})$ have the [[Language of a Grammar]] $B$ with $V_{1}≠V_{2}$

Construct a new [[Context-Free Grammar]] $G=(V,\Sigma,R,S)$: $$\begin{align*}
V&= V_{1}\cup V_{2}\cup\{S\}\\
R&= R_{1}\cup R_{2}\cup\{S \rightarrow S_{1}|S_{2}\}
\end{align*}$$
If $w\in A$, then $G_{1}$ [[Derive]]s $w$, $S_{1}\xRightarrow{*}w$, so $G$ [[Derive]]s $w$ by $S \implies S_{1}\xRightarrow{*}w$.
If $w\in B$, then $G_{2}$ [[Derive]]s $w$, $S_{2}\xRightarrow{*}w$, so $G$ [[Derive]]s $w$ by $S \implies S_{2}\xRightarrow{*}w$

If $w\in L(G)$, then either $S\implies S_{1}\xRightarrow{*}w$ or $S\implies S_{2}\xRightarrow{*}w$. Thus, $w\in A\cup B$.

Concatenation:
Let $G_{1}=(V_{1},\Sigma,R_{1},S_{1})$ generate $A$ and $G_{2}=(V_{2},\Sigma,R_{2},S_{2})$ generate $B$ with $V_{1}≠V_{2}$.

Construct a new [[Context-Free Grammar]] $G=(V,\Sigma,R,S)$ where $$\begin{align*}
V&= V_{1}\cup V_{2}\cup\{S\}\\
R&= R_{1}\cup R_{2}\cup\{S\rightarrow S_{1}S_{2}\}
\end{align*}$$
