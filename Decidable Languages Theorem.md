---
mathLink: decidable languages theorem
---
>[!thm]
>The [[Language]]s 
>- [[ADFA]]
>- [[ANFA]]
>- [[AREX]]
>- [[EDFA]]
>- [[EQDFA]]
>- [[ACFG]]
>- [[ECFG]]
>- any [[Context-Free Languages]] 
>- [[ALBA]]
>- $A=\{\langle G,H|G \text{ and }H \text{ are CFGs and }L(G)\ne L(H)\}$
>
>are [[Decide]]able

$INF_{\text{DFA}}=\{\langle M\rangle|M \text{ is a DFA whose language is infinite}\}$.
On input $\langle M\rangle$:
1. Construct a [[Deterministic Finite Automaton]]: $N$ that recognizes $$\{w|w\in L(M)\text{ and }|w|<p\}$$where $p$ is the [[Pumping Length]] of $M$.
2. Run the [[Decider]] for [[EQDFA]] on $\langle M,N\rangle$. 

>[!proof]

[[ADFA]]:
Let $M$ be a [[Deterministic Finite Automaton]]. The following [[Algorithm]] [[Decide]]s the [[Language of Machine]] $M$:
On input $\langle M,w\rangle$:
1. Simulate $M$ on input $w$:
	1. First, check if $M$ is a valid representation of a DFA (we would need to show that $\{\langle M\rangle|M\text{ is a DFA}\}$ is [[Turing-Decidable]])
	2. Simulate $M$ on $w$ by keeping track of the position in the input and the current state. 
2. If the simulation ends in an [[Accept]] state, accept. If it ends in a non-accept state, reject. 

[[ANFA]]:
On input $\langle N,w\rangle$:
1. Convert $N$ to an [[Equivalent Machines]] [[Deterministic Finite Automaton]] $M$
2. Run the [[Decider]] for [[ADFA]] on $\langle M,w\rangle$. Accept if it accepts, and reject if it rejects. 

[[AREX]]:
On input $\langle R,w\rangle$:
1. Convert $R$ to an [[Equivalent Machines]] [[Nondeterministic Finite Automaton]] $N$.
2. Run the [[Decider]] for [[ANFA]] on $\langle N,w\rangle$. Accept if it accepts, and reject if it rejects.

[[EDFA]]:
On input $\langle M\rangle$:
1. For each [[String]] $w$ in $\Sigma^{*}$ with $|w|$ less than or equal to the number of states of the DFA:
	1. run the decider for [[ADFA]] on $\langle M,w\rangle$. Accept if it accepts
2. Reject

Since $L(M)$ is [[Regular Language]], the [[Pumping Lemma]] for [[Regular Language]] [[Language]]s implies that this is a correct construction.

[[EQDFA]]:
On input $\langle M_{1},M_{2}\rangle$:
1. Create a [[Deterministic Finite Automaton]] $M$ which recognizes the [[Symmetric Difference]] of the [[Language]]s of $M_{1}$ and $M_{2}$.
2. Run the [[Decider]] for [[EDFA]] on $\langle M\rangle$. Accept if it accepts and reject if it rejects

The [[Regular Operation]]s show that we can construct $M$.

[[ACFG]]:
On input $\langle G,w\rangle$:


[[ECFG]]:
On input $\langle G\rangle$:
1. Convert $G$ to an [[Equivalent Machines]] [[Context-Free Grammar]] $G'$ in [[Chomsky Normal Form]].
2. For each [[String]] in $\Sigma^{*}$ with $|w|$ less than or equal to the [[Pumping Length]] of $G'$:
	1. run the decider for [[ACFG]] on $\langle G,w\rangle$. Accept if it accepts
3. Reject

Since $L(G)$ is a [[Context-Free Languages]], the [[Pumping Lemma for Context-Free Languages]] implies that this is a correct construction.

$A$:
For each integer $0\le n<\infty$:
1. For each [[String]] $w$ with $|w|\le n$, run the [[Decider]] for $A_{CFG}$ on each of $\langle G,w\rangle$ and $\langle H,w\rangle$. If it accepts on one and rejects on the other, accept.

If the languages are different, there exists a finite $w$ that is in one of the languages and not the other. Thus, this will accept.