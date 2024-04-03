>[!1]

Original [[Context-Free Grammar]]: $$\begin{align*}
T&\rightarrow \texttt{aa}T \texttt{b}\ |\ U\ |\ \varepsilon\\
U&\rightarrow \texttt{bb}U \texttt{a}\ |\ T\ |\ \varepsilon
\end{align*}$$I am assuming that the start variable is $T$.
START:
$$\begin{align*}
S&\rightarrow T\\
T&\rightarrow \texttt{aa}T \texttt{b}\ |\ U\ |\ \varepsilon\\
U&\rightarrow \texttt{bb}U \texttt{a}\ |\ T\ |\ \varepsilon
\end{align*}$$
BIN: 
Remove $T \rightarrow \texttt{aa}T \texttt{b}$:
$$\begin{align*}
S&\rightarrow T\\
T&\rightarrow \texttt{a}A\ |\ U\ |\ \varepsilon\\
A&\rightarrow \texttt{a}T \texttt{b}\\
U&\rightarrow \texttt{bb}U \texttt{a}\ |\ T\ |\ \varepsilon
\end{align*}$$
Remove $A \rightarrow \texttt{a}T \texttt{b}$:
$$\begin{align*}
S&\rightarrow T\\
T&\rightarrow \texttt{a}A\ |\ U\ |\ \varepsilon\\
A&\rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\\
U&\rightarrow \texttt{bb}U \texttt{a}\ |\ T\ |\ \varepsilon
\end{align*}$$
Remove $U \rightarrow \texttt{bb}U \texttt{a}$:
$$\begin{align*}
S&\rightarrow T\\
T&\rightarrow \texttt{a}A\ |\ U\ |\ \varepsilon\\
A&\rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\\
U&\rightarrow \texttt{b}C\ |\ T\ |\ \varepsilon\\
C&\rightarrow \texttt{b}U \texttt{a}
\end{align*}$$
Remove $C \rightarrow \texttt{b}U \texttt{a}$:
$$\begin{align*}
S&\rightarrow T\\
T&\rightarrow \texttt{a}A\ |\ U\ |\ \varepsilon\\
A&\rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\\
U&\rightarrow \texttt{b}C\ |\ T\ |\ \varepsilon\\
C&\rightarrow \texttt{b}\\
D&\rightarrow U \texttt{a}
\end{align*}$$
DEL-$\varepsilon$: 
Delete $T \rightarrow \varepsilon$:
$$\begin{align*}
S&\rightarrow T\ |\ \varepsilon\\
T&\rightarrow \texttt{a}A \ |\ U\\
A& \rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\ |\ \texttt{b}\\
U&\rightarrow \texttt{b}C \ |\ T\ |\ \varepsilon\\
C&\rightarrow \texttt{b}D\\
D&\rightarrow U \texttt{a}
\end{align*}$$
Delete $U \rightarrow \varepsilon$:
$$\begin{align*}
S&\rightarrow T\ |\ \varepsilon\\
T&\rightarrow \texttt{a}A \ |\ U\\
A& \rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\ |\ \texttt{b}\\
U&\rightarrow \texttt{b}C\ |\ T\\
C&\rightarrow \texttt{b}D\\
D&\rightarrow U \texttt{a}\ |\ \texttt{a}
\end{align*}$$
UNIT:
Remove $T \rightarrow U$:
$$\begin{align*}
S&\rightarrow T\ |\ \varepsilon\\
T&\rightarrow \texttt{a}A \ |\ \texttt{b}C\\
A& \rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\ |\ \texttt{b}\\
U&\rightarrow \texttt{b}C\ |\ T\\
C&\rightarrow \texttt{b}D\\
D&\rightarrow U \texttt{a}\ |\ \texttt{a}
\end{align*}$$
Remove $U \rightarrow T$:
$$\begin{align*}
S&\rightarrow T\ |\ \varepsilon\\
T&\rightarrow \texttt{a}A \ |\ \texttt{b}C\\
A& \rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\ |\ \texttt{b}\\
U&\rightarrow \texttt{b}C\ |\ \texttt{a}A\\
C&\rightarrow \texttt{b}D\\
D&\rightarrow U \texttt{a}\ |\ \texttt{a}
\end{align*}$$
Remove $S \rightarrow T$:
$$\begin{align*}
S&\rightarrow \texttt{a}A\ |\ \texttt{b}C\ |\ \varepsilon\\
T&\rightarrow \texttt{a}A \ |\ \texttt{b}C\\
A& \rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\ |\ \texttt{b}\\
U&\rightarrow \texttt{b}C\ |\ \texttt{a}A\\
C&\rightarrow \texttt{b}D\\
D&\rightarrow U \texttt{a}\ |\ \texttt{a}
\end{align*}$$
TERM:
$$\begin{align*}
S&\rightarrow EA\ |\ FC\ |\ \varepsilon\\
T&\rightarrow EA \ |\ FC\\
A& \rightarrow EB\\
B&\rightarrow T F\ |\ \texttt{b}\\
U&\rightarrow FC\ |\ EA\\
C&\rightarrow FD\\
D&\rightarrow U E\ |\ \texttt{a}\\
E&\rightarrow \texttt{a}\\
F&\rightarrow \texttt{b}
\end{align*}$$

>[!2]

Let $G=(V,\Sigma,S,R)$ be a [[Context-Free Grammar]] in [[Chomsky Normal Form]].

Let $P(n)$ be that if a variable $A\in V$ derives a string $w$ with $|w|=n$, then this derivation takes exactly $2n-1$ steps.

Base Case: $n=1$. 
Let $w\in \Sigma$ and $A\in V$ with $A\xRightarrow{*} w$. The only possible derivation of $w$ is $$A\implies w=t\in \Sigma$$If the first step of a derivation of $w$ was $A \Rightarrow TU$ for $T,U\in V-\{S\}$, then $|w|\ge 2$, since neither $T \xRightarrow{*} \varepsilon$ nor $V \xRightarrow{*} \varepsilon$. Since the only possible derivation of $w$ by $A$ is one step, $P(1)$ holds.

Inductive Step: Let $n\ge1$ be given and suppose $P(k)$ holds for all $1\le k\le n$.
Let $w\in\Sigma^{*}$ and $A\in V$ with $A\xRightarrow{*}w$ and $|w|=n+1$. We may write $$A\implies TU$$for some [[Variable]]s $T,U\in V-\{S\}$. Since neither $T\xRightarrow{*}\varepsilon$ nor $U\xRightarrow{*}\varepsilon$, let $$T\xRightarrow{*} x$$and $$U\xRightarrow{*} y$$such that $$w=xy$$Since $1\le|y|\le n$ and $1\le|x|\le n$, the inductive hypothesis lets us count the total number of steps in this derivation: $$A\implies TU\xRightarrow{*} xU\xRightarrow{*}xy=w$$The first [[Yield]] is one step. The derivation of $x$ is $2|x|-1$ steps, and the derivation of $y$ is $2|y|-1$ steps. In total, we have $$1+2|x|-1+2|y|-1=2(|x|+|y|)-1=2(|w|)-1=2(n+1)-1$$showing $P(n+1)$.

By the strong [[Principle of Mathematical Induction]], $P(n)$ for all $n\in \mathbb{N}$.

Applying $P$ for the case where $A=S$ gives the desired claim.

>[!3]

>[!prop]
>Let $M=(Q,\Sigma,\delta,q_{0},F)$ be a [[Deterministic Finite Automaton]]. The following procedure generates a [[Context-Free Grammar]] $G$ which recognizes $\text{Sort}(L(M))$. 
>1. Make a [[Variable]] $R_{i}$ for each [[States]] $q_{i}\in Q$.
>2. Add the [[Substitution Rule]] $R_{i}\rightarrow \texttt{a} R_{j}$ to the [[Context-Free Grammar]] if $\delta(q_{i},\texttt{a})=q_{j}$ is a transition in the [[Deterministic Finite Automaton]]
>3. Add the [[Substitution Rule]] $R_{i}\rightarrow R_{j}\texttt{b}$ to the [[Context-Free Grammar]] if $\delta(q_{i},\texttt{b})=q_{j}$ is a transition in the [[Deterministic Finite Automaton]]
>4. Add the [[Substitution Rule]] $R_{i}\rightarrow \epsilon$ if $q_i$ is an [[Accept]]ed [[States]]. 
>5. Make $R_0$ the [[Start Variable]] of $G$

