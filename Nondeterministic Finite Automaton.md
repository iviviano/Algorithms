---
mathLink: nondeterministric finite automaton
---
>[!def]
>A *nondeterministic finite automaton* is a $5$-[[Tuple]] $(Q,\Sigma,\delta,q_{0},F)$ where
>1. $Q$ is a finite [[Set]] of [[States]]
>2. $\Sigma$ is a finite [[Alphabet]]
>3. $\delta:Q\times \Sigma_{\epsilon}\rightarrow\mathcal{P}(Q)$ is the [[Transition Function]]
>4. $a_{0}\in Q$ is the [[Start State]]
>5. $F\subseteq Q$ is the [[Set of Accept States]]

>[!note]
>- $\Sigma_{\epsilon}=\Sigma\cup\{\epsilon\}$, where $\epsilon$ is the empty [[String]]
>- $\mathcal{P}(Q)$ refers to the [[Power Set]] of $Q$

