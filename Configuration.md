---
mathLink: configuration
---
>[!def]
>For a [[Turing Machine]], a setting of a current state, current [[Tape]] contents, and current [[Head]] location is called the *configuration*.

>[!not]
>For a state $q$ and two [[String]]s $u$ and $v$ over the [[Tape]] [[Alphabet]], write the configuration as $u\ q\ v$ where the current state is $q$, the tape contents is $uv$, and the current head location is the first [[Symbol]] of $v$.

>[!note]
>$u\in \Sigma^*$ is the tape to the left of the [[Head]]
>$q\in Q$ is the current state
>$v\in \Gamma^*$ is the portion of the tape under the [[Head]] and to the left.