---
mathLink: Turing-recognizable
---
>[!def]
>A [[Language]] is *Turing-recognizable* if some [[Turing Machine]] [[Recognize]]s it.

>[!note]
>This is also called *recursively enumerable*.

>[!example]

$$A=\{\langle p\rangle|\text{ there is some assignment of integers to variables such that }p=0\}$$
$A$ is recognized by the [[Turing Machine]]:
On input $\langle p\rangle$:
1. For $0\le n<\infty$, for all combinations $|x_{1}|,\ldots,|x_{n}|\in[n]$, if $p(x_{1},\ldots,x_{n})=0$, accept.
