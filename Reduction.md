---
mathLink: reduc
---
>[!def]
>A *reduction* of a problem is the conversion to a special case of another problem and solving it that way.

>[!def]
>A problem is *[[Polynomial]] time reducible* to another problem if there exists a reduction that is [[Polynomial Run Time]].

>[!not]
>Polynomial-time reducible is denoted $≥_p$.

Examples:
1. [[Max Flow Problem]] $≥_{p}$ [[Bipartite Matching Problem]]
2. 

If $X≥_{p}Y$
- $X$ is at least as hard as $Y$
- If $X$ can be solved by a [[Polynomial Run Time]], so can $Y$
- If $Y$ is not [[Tractability]], then $X$ is not [[Tractability]].

>[!note]
>Reductions impose an ordering on hardness of problems

