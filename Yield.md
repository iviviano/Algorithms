---
mathLink: yield
---
>[!def]
>If $u,v,w$ are [[String]]s of [[Variable]]s and [[Terminal]]s, and $A \rightarrow w$ is a [[Substitution Rule]] of the [[Context-Free Grammar]], we say that $u A v$ *yields* $uwv$, notated $$uAv\implies u w v$$

>[!def]
Take a [[Turing Machine]] $M=(Q,\Sigma,\Gamma,\delta,q_{0},q_{accept},q_{reject})$. Let $a,b,c\in \Gamma$ and $u,v\in \Gamma^{*}$. Let $q_{i},q_j$ be two [[States]]. If the [[Transition Function]] gives $$\delta(q_{i},b)=(q_{j},c,L),$$Then $ua\ q_{i}\ bv$ *yields* $u\ q_{j}\ acv$. If the [[Transition Function]] gives $$\delta(q_{i},b)=(q_{i},c,R),$$then $ua\ q_{i}\ bv$ *yields* $uac\ q_{j}\ v$.

>[!note]
>There are two special cases for [[Turing Machine]] yielding. The [[Configuration]] $q_{i}\ bv$ yields $q_{j}\ cv$ for left movement and $c\ q_{j}\ v$ for right movement. 

>[!note]
>The right end of the tape is handed normally, since $$ua\ q_{i}=ua\ q_{i}\ \sqcup$$
