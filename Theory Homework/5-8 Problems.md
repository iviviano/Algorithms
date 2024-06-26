# Prove Each Language is Undecidable

$$A=\{\langle M\rangle:M\text{ is a TM that accepts }\texttt{aba}\}$$
Suppose $A$ is [[Decide]]able with [[Decider]] $R$. The following [[Turing Machine]] [[Decide]]s [[ATM]]:

On input $\langle M,w\rangle$:
1. Construct a [[Turing Machine]] $M'$: on input $\langle x\rangle$:
	1. If $x=\texttt{aba}$, simulate $M$ on $w$. Accept if it accepts, and reject if it rejects.
	2. Otherwise, reject.
2. Run $R$ on $\langle M'\rangle$. Accept if it accepts, and reject if it rejects. 

Since $R$ accepts on $\langle M'\rangle$ [[iff]] $\texttt{aba}\in L(M')$ and $\texttt{aba}\in L(M')$ [[iff]] $w\in L(M)$, this [[Decide]]s $A$.


$$INF_\text{TM}=\{\langle M\rangle:M \text{ is infinite}\}$$
Suppose $INF_\text{TM}$ is [[Decide]]able with [[Decider]] $R$. The following [[Turing Machine]] [[Decide]]s [[ATM]]:

On input $\langle M,w\rangle$:
1. Construct a [[Turing Machine]] $M'$: on input $\langle x\rangle$:
	1. Simulate $M$ on $w$. Accept if it accepts and reject if it rejects.
2. Run $R$ on $\langle M'\rangle$. Reject if it accepts, and accept if it rejects. 


>[!thm] Theorem (Rice's theorem)
The language representing a decision problem of describing any nontrivial property of [[Turing Machine]] is un[[Decide]]able.


$$B=\{\langle M, w\rangle:M \text{ is a TM that writes a blank symbol over a non-blank}\}$$
Suppose $B$ is [[Decide]]able with [[Decide]]r $R$. The following [[Turing Machine]] [[Decide]]s [[ATM]]:

On input $\langle M,w\rangle$:
1. Construct a [[Turing Machine]] $M'$: on input $\langle x\rangle$:
	1. Simulate $M$ on $w$ without using the first position of the input tape and using a different symbol to represent blanks. If it accepts, write $\textvisiblespace$ on the first position of the input tape.
	2. Loop
2. Run $R$ on $\langle M',a\rangle$. Accept if it accepts, and reject otherwise.


$$B=\{\langle P\rangle|P \text{ is a Python program that prints "Hello world!"}\}$$
Suppose $B$ is [[Decide]]able with [[Decider]] $R$. The following [[Turing Machine]] [[Decide]]s [[ATM]]:

On input $\langle M,w\rangle$:
1. Construct a $P$: 
	1. Simulate $M$ on $w$. If $M$ ever accepts, print "Hello world!"
2. Run $R$ on $\langle P\rangle$. Accept if it accepts and reject otherwise.

