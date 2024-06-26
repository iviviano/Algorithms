---
mathLink:
---
>[!thm]
>The [[Language]] [[ETM]] is [[Co-Turing-Recognizable]].

>[!proof]

The following [[Turing Machine]] [[Recognize]]s the [[Compliment]] of [[ETM]]:
On input $\langle M\rangle$, 
1. If $\langle M\rangle$ is not a valid representation of a [[Turing Machine]], [[Accept]].
2. For each $k\in \mathbb{N}$, run $M$ on each $w\in \Sigma^{*}$ with $|w|≤k$ for $k$ steps. If it ever accepts, [[Accept]].

>[!prop] Corollary
Since the [[Undecidable Languages Theorem]] says [[ETM]] is [[Undecidable]], the [[Decidable Language Characterization Theorem]] shows that [[ETM]] is unrecognizable.

