>[!1]


Let $M$ be a [[Turing Machine]]. Simulate $M$ on a Turing machine with a doubly infinite tape by 
1. Read the first symbol on the tape, write it back to the tape, and move left.
2. Write a $\texttt{\$}\notin \Gamma$ on the tape and move right.
3. Compute as normal on $M$ except whenever the symbol under the head is $\texttt{\$}$, write a $\texttt{\$}$ and move right.

Let $M$ be a Turing machine with double infinite tape. Simulate $M$ on a normal [[Turing Machine]] by 
1. Compute as normal on $M$ except whenever the head tries to move left on the leftmost position of the tape, copy every symbol one position to the right, write a $\textvisiblespace$ on the first space of the tape, and place the head on the first symbol of the tape.


>[!2]

The idea is to have stack 1 contain the tape to the left of the head and stack 2 contain the tape to right of the head. The PDA constructed has the same set of states as the Turing machine with some additional ones to handle pushing multiple symbols and reading the input onto the stack. The PDA has stack alphabet $\Gamma\cup\{\texttt{\$}\}$. It has one accept state $q_{accept}$. 

Start computation by pushing $\texttt{\$}$ onto both stacks. Read the whole input onto stack 1. Then, reverse its direction by popping symbols from stack 1 and pushing them onto stack 2 until stack 1 has only a $\texttt{\$}$. Now, we simulate $M$. 

We are done reading input, so all following read transitions are $\varepsilon$. 

For a configuration $q,s_{1}\ne \texttt{\$},s_{2}$ of the PDA, if $$\delta(q,s_{2})=(q',s,L)$$
we push $s$ onto stack 2, then, push $s_{1}$ onto stack 2 (the double push is handled with an extra state). Nothing is pushed onto stack 1. The PDA's state changes to $q'$.
In the configuration $q,\texttt{\$},s_2$ of the PDA, with $$\delta(q,s_{2})=(q',s,L)$$
we push $s$ onto stack 2 and push $\texttt{\$}$ onto stack 1. The PDA's state is changed to $q'$.

For a configuration $q,\varepsilon,s_{2}\ne\texttt{\$}$ of the PDA, if 
$$\delta(q,s_{2})=(q',s,R)$$
we push $s$ onto stack 1. The PDA's state is changed to $q'$.
In the configuration $q,\varepsilon,\texttt{\$}$ of the PDA, if 
$$\delta(q,\textvisiblespace)=(q',s,R)$$we push $s$ onto stack 1 and push $\texttt{\$}$ onto stack 2. The PDA's state is changed to $q'$.


>[!3]

(a) Concatenation: Let $M_{1}$ be a [[Turing Machine]] [[Decide]]ing [[language]] $A_{1}$ and $M_{2}$ be a [[Turing Machine]] [[Decide]]ing the [[language]] $A_{2}$. The following algorithm [[Decide]]s the [[Language Concatenation]]ion $A_{1}A_{2}$:
On input $w$,
1. For each division $w=xy$, run $M_{1}$ on $x$. If it accepts, run $M_{2}$ on $y$. If it accepts, accept. Otherwise, continue with the next division.
2. If we don't accept for any division, reject.

(b) Kleene Star: Let $M$ be a [[Turing Machine]] that [[Decide]]s a [[Language]] $A$. The following [[Algorithm]] [[Decide]]s the Kleene [[Star]] $A^{*}$:
On input $w$, 
1. For each division $w=w_{1}\cdots w_{n}$ with $n\le|w|$, if $M$ accepts on all of $w_{1},\ldots,w_{n}$, accept.
2. Reject

(c) Compliment: Let $M=(Q,\Sigma,\Gamma,\delta,q_{0},q_{accept},q_{reject})$ be a [[Turing Machine]] that [[Decide]]s the [[Language]] $A$. Then, $M'=(Q,\Sigma,\Gamma,\delta,q_{0},q_{reject},q_{accept})$ is a [[Turing Machine]] that [[Decide]]s the [[Language]] $\Sigma^{*}\setminus A$.

(d) Intersection. Let $M_{1}$ be a [[Turing Machine]] that [[Decide]]s the [[Language]] $A_{1}$ and let $M_{2}$ be a [[Turing Machine]] that [[Decide]]s the [[Language]] $A_{2}$. The following [[Algorithm]] [[Decide]]s the [[Intersection]] $A_{1}\cap B_{2}$:
On input $w$,
1. Run $M_{1}$ on $w$. If it rejects, reject. 
2. Run $M_{2}$ on $w$. If it rejects, reject. If it accepts, accept.


>[!4]

(a) Concatenation: Let $M_{1}$ be a [[Turing Machine]] that [[Recognize]]s a [[Language]] $A_{1}$ and $M_{2}$ be a [[Turing Machine]] that [[Recognize]]s a [[Language]] $A_{2}$. The following [[Algorithm]] [[Recognize]]s the [[Language Concatenation]]ion $A_{1}A_{2}$:
On input $w$,
1. For each $0\le n<\infty$,
	1. For each division $w=xy$, run $M_{1}$ for $n$ steps on $x$. If it accepts, run $M_{2}$ for $n$ steps on $y$. If it accepts, accept.

(b) Kleene Star: Let $M$ be a [[Turing Machine]] that [[Recognize]]s a [[Language]] $A$. The following [[Algorithm]] [[Recognize]]s the Kleene [[Star]] $A^{*}$:
On input $w$, 
1. For each $0\le k< \infty$,
	1. For each division $w=w_{1}\cdots w_{n}$ with $n\le|w|$, run $M$ for $k$ steps on each of $w_{1},\ldots,w_{n}$. If it accepts on all of them, accept.

(c) Intersection: Let $M_{1}$ be a [[Turing Machine]] that [[Recognize]]s the [[Language]] $A_{1}$ and let $M_{2}$ be a [[Turing Machine]] that [[Recognize]]s the [[Language]] $A_{2}$. The following [[Algorithm]] [[Recognize]]s the [[Intersection]] $A_{1}\cap B_{2}$:
On input $w$,
1. Run $M_{1}$ on $w$. If it rejects, reject. 
2. Run $M_{2}$ on $w$. If it rejects, reject. If it accepts, accept.






In office hours tonight, the similarity between `let` and `lambda` evaluation came up. We can rationalize this relationship by realizing `let` as syntactic sugar. We can implement this idea by parsing
``` scheme
(let ([S1 EXP1]
	  ...
	  [Sn EXPn])
	EXP)
```
as 
```scheme
((lambda (S1 ... Sn) EXP) EXP1 ... EXPn)
```
These are indeed equivalent: in the evaluation of both, the body expression `EXP` is evaluated in an extended environment where the symbols `S1` through `Sn` are bound to the evaluated `EXP1` through `EXPn`. I hope this helps contextualize the similarities in evaluation strategies and provides a simpler example than `letrec` to understand syntactic sugar.