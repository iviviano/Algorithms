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
$$\begin{align*}
S&\rightarrow T\\
T&\rightarrow \texttt{a}A \ |\ U\ |\ \varepsilon\\
A& \rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\\
U&\rightarrow \texttt{b}C \ |\ T\ |\ \varepsilon\\
C&\rightarrow \texttt{b}D\\
D&\rightarrow U \texttt{a}
\end{align*}$$
DEL-$\varepsilon$: 
After deleting $T \rightarrow \varepsilon$:
$$\begin{align*}
S&\rightarrow T\ |\ \varepsilon\\
T&\rightarrow \texttt{a}A \ |\ U\\
A& \rightarrow \texttt{a}B\\
B&\rightarrow T \texttt{b}\ |\ \texttt{b}\\
U&\rightarrow \texttt{b}C \ |\ T\ |\ \varepsilon\\
C&\rightarrow \texttt{b}D\\
D&\rightarrow U \texttt{a}
\end{align*}$$
After deleting $U \rightarrow \varepsilon$:
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

Let $P(n)$ be that all [[String]]s $w\in L(G)$ with [[Length]] $|w|=n$ are derived in exactly $2n-1$ steps.

Base Case: $n=1$. 
If the length of $w$ is $1$, then the only possible derivation of $w$ is $$S\implies w=t\in \Sigma$$If the first step of a derivation of $w$ was $S \rightarrow TV$, then $|w|\ge 2$, since neither $T \xRightarrow{*} \varepsilon$ nor $V \xRightarrow{*} \varepsilon$. Since the only possible derivation of $w$ are one step, $P(1)$ holds.

Inductive Step: Let $n\ge1$ be given and suppose $P(k)$ holds for all $1\le k\le n$.
Let $w\in L(G)$ with $|w|=n+1$. We may write $$S\implies TU$$for some [[Variable]]s $T,U\in V-\{S\}$. Since neither $T\xRightarrow{*}\varepsilon$ nor $U\xRightarrow{*}\varepsilon$, let $$T\xRightarrow{*} x$$and $$U\xRightarrow{*} y$$such that $$w=xy$$Since $|y|\le n$ and $|x|\le n$, the inductive hypothesis lets us count the total number of steps in this derivation: $$S\implies TU\xRightarrow{*} xU\der$$

