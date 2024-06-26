---
mathLink: Turing machine
---
>[!def]
>A *Turing machine* is a $7$-[[Tuple]], $(Q,\Sigma,\Gamma,\delta,q_{0},q_{accept},q_{reject})$, where $Q,\Sigma,\Gamma$ are finite [[Set]]s and
>1. $Q$ is the [[Set]] of [[States]]
>2. $\Sigma$ is the input [[Alphabet]] not containing the [[Blank Symbol]]
>3. $\Gamma$ is the tape [[Alphabet]], where $\textvisiblespace\in \Gamma$ and $\Sigma\subseteq \Gamma$
>4. $\delta:Q-\{q_\text{accept},q_\text{reject}\}\times \Gamma\rightarrow Q\times \Gamma\times\{L,R\}$ is the [[Transition Function]]
>5. $q_{0}\in Q$ is the [[Start State]]
>6. $q_{accept}\in Q$ is the [[Accept]] [[States]]
>7. $q_{reject}\in Q$ is the [[Reject State]], where $q_{reject}≠q_{accept}$

>[!example]

Let $D=\{w\in\{a,b\}^{*}|w \text{ has exactly twice as many }a \text{'s as }b'\text{s}\}$

1. Scan right until an unmarked a. If we never encounter an unmarked a or b, accept.
2. Scan right and mark the first unmarked a
3. Return the head to the start of the tape.
5. Scan right, marking the first two unmarked b's. If there aren't enough b's, reject
6. Return the head to the start of the tape. 
7. Return to step 1


Let $E=\{x+y=z|x,y,z \text{ are binary numbers with }x+y=z\}$

1. Set the carry state to 0
2. If the last digit of x and y are 1, set the carry to 1, assert that the last digit of z is equal to the previous carry, and mark off the last digit of each x, y, and z


Let $F=\{xyz|x,y,z \text{ are binary numbers such that }x+y=z\}$. 

- Put a + after the first digit, moving the rest of the input to the right.
- Put an = after the second digit, moving the rest of the input to the right.
- Run the $E$ machine on the tape. While it doesn't accept, try moving the = over 1 until it reaches the end.
- Once it reaches the end, swap the + sign with the digit to its right. 
- Place the equal at the earliest place it can go...
- Return to step 3
