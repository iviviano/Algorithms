Idea: build tree one edge at a time by finding lowest cost edge that connects to current tree.

>[!def]
An [[edge]] *crosses* a [[Cut]] $(S,V-S)$ if one endpoint is in $S$ and the other is in $V-S$.

>[!alg]
>$$\begin{align}
&\textbf{Algorithm } \text{Prim's Algorithm}\\
&\textbf{Input: } \text{Connected Graph }G=(V,E)\\
&\textbf{Output: } \text{Minimum Spanning Tree }T\\
&\text{Let }r\in V\\
&S=\{r\}\\
&T=\emptyset\\
&\textbf{While } S≠V \textbf{ do:}\\
&\quad \text{Add cheapest edge }e \text{ crossing the cut }(S,V-S)\text{ to }T\\
&\quad \text{Add each endpoint of }e \text{ to }S\\
&\textbf{end while}\\
&\textbf{return } T\\
\end{align}$$

>[!prop] Fact
>A [[Graph]] is [[Connected Graph]] [[iff]] it has an [[edge]] crossing every possible [[Cut]]

>[!prop] Lemma (The cut property)
Let $(S,V-S)$ be a [[Cut]], and let $e$ be the unique cheapest [[edge]] crossing this [[Cut]]. Then $e$ is in every [[Minimum Spanning Tree]]
>>[!proof]
By the fact, any [[Spanning Tree]] has some [[edge]] crossing the cut. As $e$ is the unique cheapest edge crossing the cut, if a [[Spanning Tree]] had some other [[edge]] crossing this cut, we could replace that [[edge]] with $e$ without disconnecting the [[Graph]] or adding a [[Cycle]]. As $e$ is unique, this decreases the cost of the [[Spanning Tree]]. As the cost of a [[Minimum Spanning Tree]] cannot be decreased, any [[Minimum Spanning Tree]] must contain $e$.

>[!proof] Feasibility
We must show that $T$ is [[Connected Graph]] and [[Acyclic]]. 

>[!proof] Optimality
Assume all [[edge]] weights are distinct. At each step, we added an edge that is in every [[Minimum Spanning Tree]] by the lemma. So, every added edge was correct. At the end, we got a [[Spanning Tree]], so the result has to be the [[Minimum Spanning Tree]].

