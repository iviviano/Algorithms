

Represent a [[Turing Machine]] $M$ by $\langle M\rangle\in\{0,1\}^{*}$. We can extend this to all of $\{0,1\}$ by defining $w$ to be the [[Turing Machine]] which always rejects for all invalid representations $w$. Thus, $$\{0,1\}^{*}=\{\langle M\rangle|\langle M\rangle \text{ is a TM}\}$$Since $\{0,1\}^{*}$ is countable, there are countably many [[Turing Machine]]s.

>[!thm]
>For every [[Alphabet]] $\Sigma$, the [[Set]] of [[Language]]s over $\Sigma$ is uncountable.

>[!proof]
Let $f:\mathbb{N}\rightarrow\Sigma^{*}$ be [[Bijective]]. For each [[Language]] $L$ over $\Sigma$, define an infinite [[Sequence]] $b=b_{0},b_{1},\ldots$ over $\{0,1\}$ where $$b_{i}=\begin{cases}0 & \text{if }f(i)\notin L \\
1 & \text{if }f(i) \in L\end{cases}$$
Thus, the cardinality of the number of languages over $\Sigma^{*}$ is atleast that of the set of binary sequences. And, [[Binary Sequences are Uncountable]]. 

>[!thm]
The [[Language]] $$\text{DIAG}=\{\langle M\rangle|M \text{ is a TM and does not accept }\langle M\rangle\}$$is [[Undecidable]].

>[!proof]

Assume that $D$ [[Decide]]s $\text{DIAG}$.

Suppose $D\in\text{DIAG}$. Then, since $D$ [[Decide]]s $\text{DIAG}$, $D$ must [[Accept]] $\langle D\rangle$. This contradicts the definition of $\text{DIAG}$.

If $D\notin \text{DIAG}$, then since $D$ [[Decide]]s $\text{DIAG}$, $D$ must [[Reject]] $\langle D\rangle$. Bu if $D$ [[Reject]]s $\langle D\rangle$, then by definition, $\langle D\rangle\in\text{DIAG}$.

>[!note] 
>This proof can easily be changed to show that $\text{DIAG}$ is not [[Turing-Recognizable]]. 

