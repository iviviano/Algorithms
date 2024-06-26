---
mathLink: equivalence of NTMs and DTMs
---
>[!thm]
>Every [[Nondeterministic Turing Machine]] has an [[Equivalent Machines]] deterministic [[Turing Machine]].

We can use a 3-[[Multitape Turing Machine]] to simulate a [[Nondeterministic Turing Machine]]. 
1. The input tape which never changes
2. The working tape will be used to simulate the [[Nondeterministic Turing Machine]]'s tape along a particular nondeterministic branch of computation
3. The address tape identifies the current branch of computation in the tree of [[Configuration]]s

$M=$ on input $w$:
1. Initially, the input tape contains $w$ and all others are empty
2. copy the input tape to the work tape and return the work tape's head to the start
3. simulate $N$ on the work tape. For each step, let $m$ be the symbol under the address tape's head. $m$ indicates which of the (at most $b$) nondeterministic choices to take this step.
	1. If $N$ enters an accepting configuration, halt and accept
	2. If $N$ enters a rejecting configuration, stop the simulation and go to step 5
	3. If the cell under the address tape head is $\textvisiblespace$ or is greater than the actual choices $N$ could make from the current configuration, stop the simulation and goto step 5
4. Otherwise, move to the $m$'th next configuration, move the address tape head to the right one cell and continue the simulation.
5. Increment the address tape and go to step 2

If $N$ accepts then $M$ accepts. If $N$ loops or rejects, then $M$ loops.

>[!note]
>Note that this construction of $M$ does not [[Decide]] the [[Language of Machine]] $N$, even if $N$ is a [[Decider]]. But, we can fix this by keeping track of all of how all of the branches end. 
