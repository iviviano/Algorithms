>[!note] 1

(a) idea: use max flow to find min cut. Add one to capacity of min cut. Keep track of which edges have been changed. Continue until $|f|=T$. If none of the edges crossing the min cut have been changed, this is a cut of capacity exactly $T$. (Does this guarantee there isn't one if some of the edges have changed?)

(b) reduce to circulation with lower bounds

$$\begin{align*}
&\textbf{Algorithm } \text{Daycare}\\
&\textbf{Input: } \text{Children }i,\text{ min handlers }W_{i},\text{ workers }j,\text{ max children }K_{j},\text{ compatible children }S_{j}\\
&\text{Let }V=\{s,t\},E=\emptyset\\
&d(v)=0,d(s)=0\\
&\textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad \text{Add }i \text{ to }V\\
&\quad d(i)=0\\
&\quad \text{Add }e=(s,t)\text{ to }E\\
&\quad c(e)=m\\
&\quad l(e)=W_{i}\\
&\textbf{end for}\\
&\textbf{For } n+1\le j\le n+m \textbf{ do:}\\
&\quad \text{Add }j \text{ to }V\\
&\quad d(j)=0\\
&\quad \text{Add }e=(j,t)\text{ to }E\\
&\quad c(e)=K_{j}\\
&\quad l(e)=0\\
&\quad \textbf{For } v\in S_{j} \textbf{ do:}\\
&\quad \quad \text{Add }e=(v,j)\text{ to }E\\
&\quad \quad c(e)=1\\
&\quad \quad l(e)=0\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\text{Add }e=(t,s)\text{ to }E\\
&c(e)=m\\
&l(e)=0\\
&\text{Let }G=(V,E)\\
&\textbf{return } \exists \texttt{circulation\_lower\_bounds}(G,c,l,d)\\
\end{align*}$$



Suppose there is a valid circulation $s$ in $G$. 



Suppose there is a valid assignment of children to employees.

(c) 
Do above for the subset of teachers in $A,B,C$, but only assign each child to one employee of each type. If that was possible, create a new network removing the edges used, $W_{i}=W_{i}-3$, $K_{j}=K_{j}-$ number of kids assigned to $j$.

>[!note] 2

$$\texttt{OPT}(i,j)=l(j)-l(i)-1+\max\{\texttt{OPT}(i+1,j),\texttt{OPT}(i,j-1)\}$$
Base cases: $\texttt{OPT}(i,i)=0$ for all $i$. 

Goal: compute $\texttt{OPT}(0,k+1)$



>[!note] 3

Let $P_{i}$ be a collection of paths. We want to know if there are $k$ paths that don't overlap.

Make a vertex $i$ for each $P_{i}$. For each $i,j$, add an edge $e=\{i,j\}$. Let $w(e)=1$ if $P_{i}\cap P_{j}=\emptyset$ and $w(e)=0$ if $P_{i}\cap P_{j}≠\emptyset$.

Return true iff there is a collection of $k$ vertices such that the weight of any edge between them is at least 1.