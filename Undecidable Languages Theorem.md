---
mathLink: undecidable languages theorem
---
>[!thm]
>The [[Language]]s 
>- [[ATM]]
>- [[ETM]]
>- [[REGULARTM]]
>- [[EQTM]]
>- [[ELBA]]
>- [[ALLCFG]]
>- [[EQCFG]]
>
>are [[Undecidable]]

>[!proof]

[[ATM]]:
Assume [[ATM]] is [[Decide]]able with [[Decide]]r $R$. 

We build a [[Turing Machine]] $D$ that [[Decide]]s $\text{DIAG}$ from the [[Existence of Undecidable Languages]].
$D$ = On input $w$:
1. Run $R$ on $\langle M,\langle M\rangle\rangle$
2. If $R$ [[Accept]]s, [[Reject]]. Otherwise, [[Accept]].

Clearly, $D$ is a [[Decider]], since $R$ is.

If $\langle M\rangle\in \text{DIAG}$, then $\langle M\rangle\notin L(M)$, so $R$ rejects on and $D$ [[Accept]]s so $\langle M\rangle\in L(D)$.

If $\langle M\rangle\notin\text{DIAG}$, then $\langle M\rangle\in L(M)$, so $R$ [[Accept]]s and $D$ rejects, so $\langle M\rangle\notin L(D)$.

Thus, $L(D)=\text{DIAG}$. We have built a [[Decider]] for $\text{DIAG}$, which contradicts the [[Existence of Undecidable Languages]]. 

[[HALTTM]]:
Assume [[HALTTM]] is [[Decide]]able with [[Decider]] $H$.

We build a [[Turing Machine]] $D$ that [[Decide]]s [[ATM]].
On input $\langle M,w\rangle$:
1. Run $H$ on $\langle M,w\rangle$. If it rejects, reject.
2. Simulate $M$ on $w$. Accept if it accepts and reject otherwise.

[[ETM]]:
Assume [[ETM]] is [[Decide]]able with [[Decider]] $E$.

We build a [[Turing Machine]] that [[Decide]]s [[ATM]].
On input $\langle M,w\rangle$:
1. Construct a new [[Turing Machine]] $M_{w}$ = "on input $x$,
	1. Replace $x$ on the [[Tape]] with $w$ and run $M$ on $w$
	2. If $M$ [[Accept]]s, accept; If $M$ rejects, reject"
2. Run $E$ on $\langle M_{w}\rangle$.
3. If $E$ [[Accept]]s, [[Reject]]; otherwise [[Accept]].
If $w\in L(M)$, $M_{w}$ [[Recognize]]s $\Sigma^{*}$. Otherwise, $M_{w}$ [[Recognize]]s $\varnothing$. 

[[EQTM]]: [[Reduction]]e [[ETM]] to [[EQTM]].
Assume [[EQTM]] is [[Decide]]able with [[Decide]]r $EQ$.

We build a [[Turing Machine]] that [[Decide]]s [[ETM]].
On input $\langle M\rangle$:
1. Construct a [[Turing Machine]] $M'$ that [[Decide]]s $\varnothing$.
2. Return the result of $EQ$ on $\langle M,M'\rangle$.

[[REGULARTM]]:
Assume [[REGULARTM]] is [[Decide]]able with [[Decider]] $R$.

The following [[Turing Machine]] [[Decide]]s [[ATM]]:
On input $\langle M,w\rangle$:
1. Construct a new TM $M'$: On input $x$:
	1. If $x=0^{n}1^{n}$ for some $n$, accept
	2. Otherwise, run $M$ on $w$ and if $M$ accepts, accept. Otherwise, reject
2. Run $R$ on $\langle M'\rangle$ and if $R$ accepts, then accept. Otherwise, reject. 

We see that $L(M')$ is [[Regular Language]] [[iff]] $M$ accepts $w$. 

>[!note]
>This proof also works for $CF_\text{TM}$, since we just choose a non-context-free [[Language]] like $a^{n}b^{n}c^{n}$.

[[ALLCFG]]:
Assume [[ALLCFG]] is [[Decide]]able with [[Decider]] $A$.

We construct a [[Decider]] for [[ATM]]. On input $\langle M,w\rangle$: Construct a [[Context-Free Grammar]] that generates every string except a valid [[Accept]]ing configuration of $w$ by $M$. We accept if this grammar doesn't accept everything. Otherwise, we reject.