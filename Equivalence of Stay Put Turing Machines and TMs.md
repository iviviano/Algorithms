
>[!def]
>A *stay-put* Turing Machine is the same except that its [[Transition Function]] is: $$\delta:Q-\{q_\text{accept},q_\text{reject}\}\times \Gamma\rightarrow Q\times \Gamma\times\{L,S,R\}$$

>[!thm]
Stay put Turing machines [[Recognize]] the same class of [[Language]]s [[Recognize]]d as [[Turing Machine]]s.

>[!proof]
We can simulate any [[Turing Machine]] by a stay put [[Turing Machine]] by never staying put. 
>
Let $M$ be a stay-put [[Turing Machine]]. The following [[Algorithm]] [[Recognize]]s $L(M)$:
On input $w$,
>1. Run $M$ on $w$. Whenever $M$ stays, move right. Then, move left without changing the tape and resume computation.

