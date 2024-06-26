>[!1]

(a) No, since $\texttt{abaab}$ is not [[Accept]]ed by $M$.

(b) Yes, since $\texttt{bab}$ is [[Accept]]ed by $M$.

(c) No, since $\langle M\rangle$ is not of the form $\langle M,w\rangle$.

(d) No, the [[Language]] of $M$ is not empty, since $M$ [[Accept]]s $\texttt{bab}$.

(e) Yes. Obviously $M$ and $M$ [[Recognize]] the same [[Language]], since they are the same [[Machine]].

>[!2]

The following [[Turing Machine]] [[Decide]]s this [[Language]]:
On input $\langle M,R\rangle$:
1. Convert the [[Regular Expression]] $R$ to an [[Nondeterministic Finite Automaton]] $N$.
2. Convert the NFA $N$ to a DFA $M_{2}$. 
3. Run the [[Decider]] for [[EQDFA]] on $\langle M,M_{2}\rangle$. [[Accept]] if it [[Accept]]s, and [[Reject]] if it [[Reject]]s.

>[!3]

The following [[Turing Machine]] [[Decide]]s the [[Language]] $\text{ALL}_{\text{DFA}}$:
On input $\langle M\rangle$:
1. Run the [[Decider]] in problem 2 on the input $\langle M,\Sigma^{*}\rangle$. Accept if it accepts, and reject it it rejects.

>[!4]

The following [[Turing Machine]] [[Decide]]s the [[Language]] $A_{\varepsilon_\text{CFG}}$:
On input $\langle G\rangle$:
1. Convert $G$ to an [[Equivalent Machines]] [[Context-Free Grammar]] $G'=(V,\Sigma,R,S)$ in [[Chomsky Normal Form]].
2. If $(S \rightarrow \varepsilon)\in R$, accept. Otherwise, reject.

>[!5]

The following [[Turing Machine]] [[Decide]]s the [[Language]] $A$:
On input $\langle R,S\rangle$:
1. Convert $R$ and $S$ to a [[Deterministic Finite Automaton]] $M_{R}$ and $M_{S}$.
2. Generate the DFA $M_{R\cap S}$ which [[Recognize]]s the [[Regular Language]] [[Language]] $L(M_{R})\cap L(M_{S})$.
3. Run the [[Decider]] for $EQ_{\text{DFA}}$ on the input $\langle M_{R}, M_{R\cap S}\rangle$. Accept if it accepts, and reject if it rejects.

Note that for step 2, we use the construction in the proof that [[Intersection]]s of [[Regular Language]] [[Language]]s are regular. 