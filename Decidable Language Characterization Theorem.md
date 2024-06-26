---
mathLink: decidable language characterization theorem
---
>[!thm]
>A [[Language]] is [[Turing-Decidable]] [[iff]] it is [[Turing-Recognizable]] and [[Co-Turing-Recognizable]].

>[!prop] Corollary
>The [[Compliment]] of [[ATM]] is not [[Turing-Recognizable]]


>[!proof]

If $L$ is [[Decide]]able, its [[Compliment]] is [[Decide]]able.

If $L$ is [[Recognize]]able, then there is a some [[Turing Machine]] $M_{1}$ that [[Recognize]]s it. If $L$ is [[Co-Turing-Recognizable]], then there is some [[Turing Machine]] $M_{2}$ that [[Recognize]]s $\bar{L}$.

The following [[Turing Machine]] [[Decide]]s $L$:
1. Run $M_{1}$ and $M_{2}$ simultaneously on $w$
2. If $M_{1}$ [[Accept]]s, [[Accept]]. If $M_{2}$ [[Accept]]s, [[Reject]].
