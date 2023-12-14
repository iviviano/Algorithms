>[!note] 1

(a) idea: use max flow to find min cut. Add one to capacity of min cut. Keep track of which edges have been changed. Continue until $|f|=T$. If none of the edges crossing the min cut have been changed, this is a cut of capacity exactly $T$. (Does this guarantee there isn't one if some of the edges have changed?)

(b) reduce to circulation with lower bounds

(c) edges from child to each specialty with lower bound 1

>[!note] 2

$$\texttt{OPT}(i,j)=l(j)-l(i)-1+\max\{\texttt{OPT}(i+1,j),\texttt{OPT}(i,j-1)\}$$
Base cases: $\texttt{OPT}(i,i)=0$ for all $i$. 

Goal: compute $\texttt{OPT}(0,k+1)$



>[!note] 3

Let $P_{i}$ be a collection of paths. We want to know if there are $k$ paths that don't overlap.

Make a vertex $i$ for each $P_{i}$. For each $i,j$, add an edge $e=\{i,j\}$. Let $w(e)=1$ if $P_{i}\cap P_{j}=\emptyset$ and $w(e)=0$ if $P_{i}\cap P_{j}≠\emptyset$.

Return true iff there is a collection of $k$ vertices such that the weight of any edge between them is at least 1.