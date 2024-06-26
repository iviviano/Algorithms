>[!1]

Assume [[EQCFG]] is [[Decide]]able with [[Decider]] $E$. The following [[Turing Machine]] [[Decide]]s [[ALLCFG]]:

On input $\langle G\rangle$:
1. Construct a grammar $G'$ which recognizes $\Sigma^{*}$.
2. Run $E$ on $\langle G,G'\rangle$. Accept if it accepts, and reject if it rejects.

For (1), we can use the DFA to [[Context-Free Grammar]] conversion.

>[!2]

Assume $T$ is [[Decide]]able with [[Decider]] $D$. The following [[Turing Machine]] [[Decide]]s [[ATM]]:

On input $\langle M,w\rangle$:
1. Let $M'$ be the [[Turing Machine]]: On input $x$:
	1. If $x=w$, accept. 
	2. If $x=w^\mathcal{R}$, run $M$ on $w$. If it accepts, accept.
	3. Reject.
2. Run $D$ on $\langle M'\rangle$. Accept if it accepts, and reject if it rejects. 

>[!3]

$$A=\{\langle J\rangle:J \text{ is a Java program that throws and exception when run}\}$$
Assume $A$ is [[Decide]]able with [[Decide]]r $D$. The following [[Turing Machine]] [[Decide]]s [[HALTTM]]:

On input $\langle M,w\rangle$:
1. Construct a java program $J$:
	1. Simulate $M$ on $w$. If $M$ [[Halt]]s, throw an exception.
2. Run $D$ on $\langle J\rangle$. Accept if it accepts and reject if it rejects. 
