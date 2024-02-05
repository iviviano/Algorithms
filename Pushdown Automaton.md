---
mathLink: pushdown automaton
---
>[!def]
>A *pushdown automaton* is a $6$-[[Tuple]] $(Q,\Sigma,\Gamma,\delta,q_{0},F)$, where $Q,\Sigma,\Gamma,F$ are finite [[Set]]s, and 
>1. $Q$ is the [[Set]] of [[States]]
>2. $\Sigma$ is the input [[Alphabet]]
>3. $\Gamma$ is the [[Stack]] [[Alphabet]]
>4. $\delta:Q\times \Sigma_{\epsilon}\times \Gamma_{\epsilon}\rightarrow\mathcal{P}(Q\times \Gamma_{\epsilon})$ is the [[Transition Function]]
>5. $q_{0}\in Q$ is the [[Start State]]
>6. $F\subseteq Q$ is the [[Set of Accept States]]

