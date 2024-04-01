---
mathLink: pumping lemma for context-free languages
---
>[!thm]
>If $A$ is a [[Context-Free Languages]], then there is a number $p$ where, if $s$ is any [[String]] in $A$ of [[Length]] at least $p$, then $s$ may be written as $s=uvxyz$ such that 
>1. for each $i≥0$, $uv^{i}xy^{i}z\in A$
>2. $|vy|>0$, and
>3. $|vxy|≤p$

>[!proof]

Let $G=(V,\Sigma,R,S)$ be a [[Context-Free Grammar]] in [[Chomsky Normal Form]] that generates a [[Language]] $A$. 

Set $p$ large enough that any [[String]] of [[Length]] at least $p$ repeats some [[Variable]] in its derivation (Using $p=2^{|V|}+1$ works)

Let $w$ be a [[String]] in $A$ with length at least $p$. Let $R$ be a repeated symbol in the derivation of $w$. 

...
$R\xRightarrow{*}x$ and $R\xRightarrow{*}vxy$
...

To see that at least of of $v$ or $y$ is not $\varepsilon$, look at $$R\xRightarrow{*} vRy$$Since $G$ is in [[Chomsky Normal Form]], we must have $R\implies AB\xRightarrow{*} vRy$ for some variables $A$ and $B$

There are two cases to consider: 
- $A\xRightarrow{*}vRs$ and $B\xRightarrow{*} t$ where $st=y$. $t$ cannot be $\varepsilon$ since $G$ is in [[Chomsky Normal Form]]
- $A\xRightarrow{*} s$ and $B\xRightarrow{*}$
This satisfies the second condition



>[!example]

Let $B=\{\texttt{a}^{n}\texttt{b}^{n}\texttt{c}^{n}|n\le0\}$. Assume $B$ is [[Pumpable]] with [[Pumping Length]] $p$. Select $w=a^{p}b^{p}c^{p}$ which is in $B$ and has [[Length]] $3p>p$. 

Now consider all possible $uvxyz=w$ with $|vy|>0$ and $$