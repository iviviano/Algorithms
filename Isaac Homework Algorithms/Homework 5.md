>[!note] 1

(a)
Step 1: Let $\text{OPT }(i)$ be the maximum value of $$\sum_{j\in J}q_{j}$$ such that $J\subseteq[i]$ has no overcrowding.

Step 2: Recurrence relation:$$\text{OPT }(i)=\max\{q_{i}+\text{OPT }(i-3),\text{OPT }(i-1)\}$$

Step 3: 

>[!proof]
If $i$ is in the optimal solution, then $i-1,i-2$ are not in the optimal solution. If $i$ is not in the optimal solution then any $[i-1]$ may be in the optimal solution. As the recurrence relation picks the case with the larger total quality, it is true for $i>2$. $i\le2$ are handled by the base cases.

Step 4: Base cases: There are three base cases. The first is $i=0$. Then, $\text{OPT }(i)=0$. If $i=1$, the sum of quality is obviously maximized by including turnip 1. This doesn't result in overcrowding, so $\text{OPT }(1)=q_{1}$. If $i=2$, we can only fit one turnip without overcrowding. So, $\text{OPT }(2)=\max\{q_{1},q_{2}\}$.

Step 5: The goal is to find $\text{OPT }(n)$.

Step 6: 

$$\begin{align*}
&\textbf{Algorithm } \text{Turnip the Heat}\\
&\textbf{Input: } \text{Qualities }q_{1},\ldots,q_{n}\\
&\textbf{Output: } \text{OPT }(n)\\
&\text{Let }A \text{ be an array of length }n+1\\
&A[0]=0;A[1]=q_{1};A[2]=\max\{q_{1},q_{2}\}\\
&\textbf{For } 2<i\le n\textbf{ do:}\\
&\quad A[i]=\max\{A[i-3]+q_{i},A[i-1]\}\\
&\textbf{end for}\\
&\textbf{return } A[n]\\
\end{align*}$$
Step 7: 

Everything outside the loop clearly has constant runtime. Each iteration of the loop also has constant runtime. As there are $n-2$ iterations of the loop, this algorithm is $O(n)$.

(b)

$$\begin{align*}
&\textbf{Algorithm } \text{Turnip the Heat}\\
&\textbf{Input: } \text{Qualities }q_{1},\ldots,q_{n}\\
&\textbf{Output: } \text{OPT }(n)\\
&\text{Let }sets \text{ be an array of length }n+1\\
&\text{Let }values \text{ be an array of length }n+1\\
&sets[0]=\emptyset; sets[1]=\{1\}\\
&\textbf{If } q_{1}>q_{2} \textbf{ then:}\\
&\quad sets[2]=\{1\}\\
&\textbf{Else}\\
&\quad sets[2]=\{2\}\\
&values[0]=0;values[1]=q_{1};values[2]=\max\{q_{1},q_{2}\}\\
&\textbf{For } 2<i\le n\textbf{ do:}\\
&\quad \textbf{If } values[i-3]+q_{i}>values[i-1] \textbf{ then:}\\
&\quad \quad sets[i]=sets[i-3]\cup\{i\}\\
&\quad \quad values[i]=values[i-3]+q_{i}\\
&\quad \textbf{Else:}\\
&\quad \quad sets[i]=sets[i-1]\\
&\quad \quad values[i]=values[i-1]\\
&\textbf{end for}\\
&\textbf{return } sets[n]\\
\end{align*}$$

 >[!note] 2 

(a) Let $V=\{a,b,c\},E=\{\{a,b\},\{b,c\}\}$. Give weights $a=2,b=3,c=2$. The greedy algorithm will choose the solution set $\{b\}$ with value $3$. However, the best solution is $\{a,c\}$ with solution $4$. 

(b) Let $V=\{a,b,c,d\},E=\{\{a,b\},\{b,c\},\{c,d\}\}$. Give weights $a=2,b=1,c=2,d=4$. This algorithm will choose the solution set $\{b,d\}$ with value $5$. However, a better solution is $\{a,d\}$ with value $6$. 

(c) 

Step 1: let $\text{OPT }(i)$ be the subset of $[i]$ such that $\{v_{j}:j\in \text{OPT }(i)\}$ is independent and has maximum total weight. If $J\subseteq[i]$, let $\text{val}(J)=\sum_{j\in J}w_{j}$.

Step 2: Recurrence relation $$\text{OPT }(i)=\begin{cases}\text{OPT }(i-2)\cup\{i\} &\text{ if } \text{val}(\text{OPT }(i-2))+w_{i}>\text{val}(\text{OPT }(i-1))\\
\text{OPT }(i-1)&\text{ otherwise}\end{cases}$$

Step 3: 

>[!proof]
Assume $i>1$. If $i≤1$, it is handled by the base cases. Vertex $i$ is either in the optimal independent set or not. If $i\in \text{OPT }(i)$, then $i-1\notin \text{OPT }(i)$, since $i$ and $i-1$ are adjacent. Therefore, $\text{OPT }(i)=\text{OPT }(i-2)\cup\{i\}$. If $i\notin \text{OPT }(i)$, then $\text{OPT }(i)=\text{OPT }(i-1)$. Now, $$\text{val}(\text{OPT }(i-2)\cup\{i\})=\text{val}(\text{OPT }(i-2))+w_{i}$$so, the recurrence relation assigns $\text{OPT }(i)$ to the highest value independent set.


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

Step 1: Let $\text{OPT }(i)$ be the maximum value of  $$\sum_{j\in S}s_{j}-C|S|$$for $S\subseteq[i]$ and $i\in S$.

Step 2: Recurrence relation:

$$\text{OPT }(i)=s_{i}-C+\max\{\text{OPT }(i-j):1\le j\le m\}$$

Step 3: 

>[!proof]
Assume $i>1$. Let $S$ be an optimal subset of the $i$ ponds. $S$ must include $i$ and $S$ must include $i-j$ for some $1\le j\le m$. I could have come to pond $i$ from any pond $i-j$ for $1\le j\le m$. The caloric surplus of my migration at any one of these ponds is given by $\text{OPT}(i-j)$. So, to find the maximum caloric surplus after gorging at pond $i$, add the shrimp at pond $i$ to the maximum of the caloric surpluses of any possible prior pond and subtract the caloric cost of traveling to pond $i$. Clearly, this is exactly what the recurrence relation gives.

Step 4: Base Case: There are two base cases. If $i=0$, then, I am at pond $0$ with no shrimp and nowhere to go. So, $\text{OPT }(i)=0$. If there is one pond, I must end at that pond. So the only possible solution has value $s_{1}-C$. 

Step 5: The goal is to find $\text{OPT }(n)$. 

Step 6: 

$$\begin{align*}
&\textbf{Algorithm } \text{Caloric Surplus of Optimal Route}\\
&\textbf{Input: } \text{Shrimp amounts }s_{1},\ldots,s_{n} \text{ and parameter }m\\
&\textbf{Output: } \text{OPT }(n)\\
&\text{Let }A \text{ be an array of length }n+1\\
&A[0]=0;A[1]=s_{1}-C\\
&\textbf{For } 1<i\le n \textbf{ do:}\\
&\quad A[i]=s_{i}-C+\max\{A[i-j]:1\le j\le m\land i-j\ge0\}\\
&\textbf{end for}\\
&\textbf{return } A[n]\\
\end{align*}$$

Step 7: 

Clearly, everything outside of the loop has constant runtime. There are at most $m$ elements of the set that is passed to $\max$. So, the body of the loop has runtime $O(m)$. As the loop runs $n$ times, the algorithm has runtime $O(mn)$.

$$\begin{align*}
&\textbf{Algorithm } \text{Optimal Route North}\\
&\textbf{Input: } \text{Shrimp amounts }s_{1},\ldots,s_{n}\text{ and parameter }m\\
&\textbf{Output: } \text{}\\
&\text{Let }ponds \text{ be an array of length }n+1\\
&\text{Let }values \text{ be an array of length }n+1\\
&ponds[0]=\emptyset;ponds[1]=\{1\}\\
&values[0]=0;values[1]=s_{1}-C\\
&\textbf{For } 1<i\le n \textbf{ do:}\\
&\quad \text{Let }best\_pond=i-1\\
&\quad \textbf{For } 1\le j\le m \textbf{ do:}\\
&\quad \quad \textbf{If } i-j<0 \textbf{ then:}\\
&\quad \quad \quad \textbf{continue}\\
&\quad \quad \textbf{If } values[i-j]>values[best\_pond] \textbf{ then:}\\
&\quad \quad \quad best\_pond=[i-j]\\
&\quad \quad \textbf{end if}\\
&\quad \textbf{end for}\\
&\quad ponds[i]=ponds[best\_value]\cup\{i\}\\
&\quad values[i]=values[best\_value]+s_{i}-C\\
&\textbf{end for}\\
&\textbf{return } ponds[n]
\end{align*}$$