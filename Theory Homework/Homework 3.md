>[!1]

>[!prop] Lemma
>Finite unions of regular languages are regular

>[!proof]
Let $\{A_{i}:1\le i\le n\}$ be a collection of regular languages. Let $P(j)$ be that $$\bigcup_{i=1}^{j}A_{i}$$is [[Regular Language]]. 
>
Base Case: $j=0$. The empty union $$\bigcup_{i=1}^{0}A_{i}=\varnothing$$Since the empty language is regular, $P(0)$ holds.
>
Inductive Step: Let $0\le j< n$ be given and suppose $P(j)$. Then, $$\bigcup_{i=1}^{j+1}A_{i}=A_{j+1}\cup\left(\bigcup_{i=1}^{j}A_{i}\right)$$Binary unions of regular languages are regular. Since $A_j+1$ is regular and $\bigcup_{i=1}^{j}A_i$ is regular by the inductive hypothesis, $P(j+1)$ holds.


Let $A$ be a finite [[Language]] over the [[Alphabet]] $\Sigma$. For each $a_{i}\in A$, write $$a_{i}=s_{1}\cdots s_{n}$$where each $s_{j}\in S$. Then, $\{a_{i}\}$ is the language of the [[Regular Expression]] $$s_{1}\cdots s_{n}$$so, $\{a_{i}\}$ is a [[Regular Language]] language. 

Since $A$ is given by the finite [[Union]] $$A=\bigcup \{a_{i}\}$$and finite unions of [[Regular Language]] [[Language]]s are [[Regular Language]] by the lemma, $A$ is [[Regular Language]].

>[!2]

(a) Let $\Sigma=\{\texttt{a}\}$ and let $A=\Sigma^{*}$. Then, $A$ is the [[Language]] of the [[Regular Expression]] $\Sigma^{*}$, so $A$ is [[Regular Language]]. $A$ is infinite since word length maps $A$ [[Surjective]]ly onto $\mathbb{N}\cup\{0\}$.

(b) There are now $\epsilon$ transitions to infinitely many branches. This requires infinitely many states, so the automaton is not finite.


>[!3]

(a) Let $N=(Q,\Sigma,\delta,q_{0},F)$ be a [[Nondeterministic Finite Automaton]]. Create a new accept state $q_a$. The new [[Nondeterministic Finite Automaton]] will have states $$Q'=Q\cup\{q_{a}\}$$For each state $q\in F$, we will add an $\varepsilon$-transition to the new accept state. The new accept state has no outgoing transitions. Formally, $\delta':Q'\times \Sigma\rightarrow Q'$ is defined by $$\delta'(q,s)=\begin{cases}\delta(q,s) & \text{if }q\in Q-F \lor (q\in Q\land s\ne \varepsilon)\\
\delta(q,s)\cup\{q_{a}\} & \text{if }q\in F \text{ and }s=\varepsilon \\
\varnothing & \text{if }q=q_{a}
\end{cases}$$
Defining $N'=(Q',\Sigma,\delta',q_{0},\{q_{a}\})$, $N'$ is a [[Nondeterministic Finite Automaton]] that [[Recognize]]s $N'$. 

(b) Let $N=$