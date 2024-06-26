---
mathLink: nondeterministic Turing machine
---
>[!def]
>A *nondeterministic Turing machine* is a $7$-[[Tuple]], $(Q,\Sigma,\Gamma,\delta,q_{0},q_{accept},q_{reject})$. The only difference from a deterministic [[Turing Machine]] is the [[Transition Function]]: $$\delta:(Q-\{q_{accept},q_{reject}\})\times \Gamma\rightarrow\mathcal{P}(Q\times\Gamma\times\{L,R\})$$

