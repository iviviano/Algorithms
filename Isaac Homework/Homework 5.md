>[!note] 1

 >[!note] 2 

(a) Let $V=\{a,b,c\},E=\{\{a,b\},\{b,c\}\}$. Give weights $a=2,b=3,c=2$. The greedy algorithm will choose the solution set $\{b\}$ with value $3$. However, the best solution is $\{a,c\}$ with solution $4$. 

(b) Let $V=\{a,b,c,d\},E=\{\{a,b\},\{b,c\},\{c,d\}\}$. Give weights $a=2,b=1,c=2,d=4$. This algorithm will choose the solution set $\{b,d\}$ with value $5$. However, a better solution is $\{a,d\}$ with value $6$. 

(c) 

Step 1: let $\text{OPT }(i)$ be the subset of $[i]$ such that $\{v_{j}:j\in \text{OPT }(i)\}$ is independent and has maximum total weight. If $J\subseteq[i]$, let $\text{val}(J)=\sum_{j\in J}w_{j}$.

Step 2: Recurrence relation $$\text{OPT }(i)=\begin{cases}\text{OPT }(i-2)\cup\{i\} &\text{ if } \text{val}(\text{OPT }(i-2))+w_{i}>\text{val}(\text{OPT }(i-1))\\
\text{OPT }(i-1)&\text{ otherwise}\end{cases}$$

Step 3: 

>[!proof]

Assume $i>1$. If $i≤1$, it is handled by the base cases. Vertex $i$ is either in the optimal independent set or not. If $i\in \text{OPT }(i)$, then $i-1\notin \text{OPT }(i)$, since $i$ and $i-1$ are adjacent. Therefore, $\text{OPT }(i)=\text{OPT }(i-2)\cup\{i\}$. If $i\notin \text{OPT }(i)$, then $\text{OPT }(i)=\text{OPT }(i-1)$. Since $\text{OPT }(i)$ is the heaviest subset of $[i]$ that contains 


Step 4: Base Cases: There are two base cases. The first is an empty vertex set. Obviously, $\text{OPT }(\emptyset)=\emptyset$ and $\text{val}(\emptyset)=0$. The second is a singleton vertex set. Obviously, $\text{OPT }(\{v_{1}\})=\{v_{1}\}$ and $\text{val}(v_{1})=w_{1}$

Step 5: The goal is to compute $\text{OPT }(n)$

Step 6: 

$$\begin{align*}
&\textbf{Algorithm } \text{Heaviest Independent Set}\\
&\textbf{Input: } \text{Vertex Set }V=\{v_{1},\ldots,v_{n}\}\\
&\textbf{Output: } \text{OPT }n\\
&\text{Let }sets \text{ be an array of length }n+1\\
&\text{Let }values \text{ be an array of length }n+1\\
&sets[0]=\emptyset; sets[1]=\{v_{1}\}\\
&values[0]=0; values[1]=w_{1}\\
&\textbf{For } 1<i\le n \textbf{ do:}\\
&\quad \textbf{If } values[i-2] + w_{i}>values[i-1] \textbf{ then:}\\
&\quad \quad sets[i]=sets[i-2]\cup\{i\}\\
&\quad \quad values[i]=values[i-2]+w_{i}\\
&\quad \textbf{Else:}\\
&\quad \quad sets[i]=sets[i-1]\\
&\quad \quad values[i]=values[i-1]\\
&\quad \textbf{end if}\\
&\textbf{end for}\\
&\textbf{return } sets[n]\\
\end{align*}$$

Step 7: Runtime

Clearly, everything outside the loop is constant. The input is already sorted with ends of the path given by $v_{1}$ and $v_{n}$ and only between consecutive vertices are adjacent. So, no preprocessing is needed. The loop executes $n-1$ times, so the algorithm is $O(n)$.

>[!note] 3


