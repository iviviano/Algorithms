---
mathLink: pumping lemma
---
>[!thm]
>If $A$ is a [[Regular Language]] [[Language]], then there is a number $p$ where if $s\in A$ with the [[Length]] of $s$ at least $p$, then $s$ may be written as $s=xyz$ with 
>1. for each $i≥0$, $xy^{i}z\in A$
>2. $|y|>0$
>3. $|xy|≤p$

>[!thm]
>If $A$ is a [[Regular Language]] [[Language]], then $A$ is [[Pumpable]].

>[!proof]

Let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]] with $L(M)=A$ and set $p=|Q|$.

If $A$ contains no strings of length at least $p$, we are done.

Otherwise, let $w$ be a string in $A$ of [[Length]] $n≥p$. Write $w_{1}\cdots w_{n}$ where each $w_{i}\in \Sigma$

Let $r_{0},r_{1},\ldots,r_{n}$ be the [[Accept]]ing computation of $M$ on $w$

By the [[Pigeonhole Principle]], pick two states $r_{j}=r_k$ with $j<k\le p$. Set $$\begin{align*}
x&= w_{1}\cdots w_{j}\\
y&= w_{j+1}\cdots w_{k}\\
z&= w_{k+1}\cdots w_{n}
\end{align*}$$
---
Let $$\delta^{*}(q,s)$$be the state the DFA ends in after reading the [[String]] $s$ after starting in the state $q$. That is $$\begin{align*}
	\delta^{*}(q,\varepsilon)&= q\\
\delta^{*}(q,cs)&= \delta^{*}(\delta(q,c),s)\quad\forall c\in \Sigma,s\in \Sigma^*
\end{align*}$$
For a repeated state $r$:
$$\begin{align*}
\delta^{*}(q_{0},x)&= r\\
\delta^{*}(r,y)&= r\\
\delta^{*}(r,z)&= q_{a}\in F\\
\delta^{*}(q_{0},xyz)&= q_{a}
\end{align*}
$$
---
Consider $\delta^{*}(xy^{i}z)$. $$\begin{align*}
\delta^{*}(q_{0},xy^{i}z&= \begin{cases}
\delta^{*}(r,z)=q_{a} & \text{ for }i=0\\
\delta^{*}(r,y^{i}z)=\delta^{*}
\end{cases}
\end{align*}$$


(2) $|y|=k-j>0$

(3) $|xy|\le p$ because $k\le p$

