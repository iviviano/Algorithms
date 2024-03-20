---
mathLink: a language is context free $\iff$ some pushdown automaton recognizes it
---
>[!thm]
>A [[Language]] is a [[Context-Free Languages]] [[iff]] some [[Pushdown Automaton]] [[Recognize]]s it.

>[!prop] Corollary
>Every [[Regular Language]] [[Language]] is a [[Context-Free Languages]]

>[!proof]

($\implies$) Let $A$ be a [[Context-Free Languages]] recognized by the [[Context-Free Grammar]] $G=(V,\Sigma,R,S)$. 

Construct a [[Pushdown Automaton]] $M=(Q,\Sigma,\Gamma,\delta,q_{0},\{q_{a}\})$ with states $Q=\{q_{0},q_{1},q_\text{loop},q_{a}\}\cup E$ where $E$ is the set of extra states used to push multiple symbols onto the stack at once. We take $\Gamma= V\cup \Sigma\cup\{\$\}$. 

Start with the transitions: $$\begin{align*}
\varepsilon,\varepsilon&\rightarrow
\end{align*}$$

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

Handle 1. by multiple transitions the transition $\varepsilon,S \rightarrow aTb$ is handled by three transitions: $$\varepsilon,S \rightarrow b; \varepsilon,\varepsilon \rightarrow T; \varepsilon,\varepsilon \rightarrow a$$
We form a [[Pushdown Automaton]] with 4 main states. State $q_{0}$ is the start, pushes \$ onto the stack. $q_1$ pushes $S$ onto the stack and transitions to $q_\text{loop}$.

For each $t\in \Sigma$, add a transition $t,t \rightarrow \varepsilon$ from $q_\text{loop}$ to $q_\text{loop}$ (this makes sure that the derived string matches the input in order, gets rid of the terminals at the start of the derived string as they appear). For each rule $A \rightarrow u_{1}\cdots u_{n}$, add $n-1$ new states and transitions to pop $A$ push $u_{n},\ldots,u_{1}$ to the stack (this derives the string by substituting when it reaches the top of the stack).

$q_\text{loop}$ transitions to $q_{a}$ with transition $\varepsilon,\$\to\varepsilon$.
