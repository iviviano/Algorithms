---
mathLink: universal Turing machine
---
>[!def]
>The [[Turing Machine]] $U$ given below is called the *universal Turing machine*. It is capable of simulating any other [[Turing Machine]] from the description of that [[Machine]].

$U$= "On input $\langle M,w\rangle$, where $M$ is a [[Turing Machine]] and $w$ is a [[String]]:"
1. [[Simulate]] $M$ on input $w$
2. If $M$ ever enters its [[Accept]] [[States]], *accept*; if $M$ ever enters its [[Reject State]], [[Reject]]
