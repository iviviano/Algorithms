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

Now consider all possible $uvxyz=w$ with $|vy|>0$ and $|vxy|\le p$
- at least one of $v$ of $y$ contains two distinct symbols. Then, $uv^{2}xy^{2}z$ contains symbols out of order, so ...
- both $v$ and $y$ contain the same symbol. Then, $uxz\notin B$, since we removed some of one type of symbol but none of the other types.
- $v$ and $y$ contain different symbols but only a single type of each. Then, $uxz\notin B$, since we removed some of two types of symbols but not the third. 


Let $D=\{a^{n}ba^{2n}ba^{3n}\}$. Assume $D$ is [[Pumpable]] with [[Pumping Length]] $p$.
Select $w=a^{p}ba^{2p}ba^{3p}$.

Now consider all possible $uvxyz=w$ with $|vy|>0$ and $|vxy|≤p$.
- If $v$ or $y$ contains a $b$, then pumping down gives too few $b$'s 
- If $x$ doesn't contain a $b$, then $vxy=a^{m}$ is in the first, second, or third run of $a$'s, for some $m$. Pumping down gives the wrong ratio
- If $x$ contains a $v$, then we can only pump of two of the runs of $a$'s, so we can pump up to the wrong ratio of $a$'s
