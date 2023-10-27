>[!note] 1

 >[!note] 2 

(a) Let $V=\{a,b,c\},E=\{\{a,b\},\{b,c\}\}$. Give weights $a=2,b=3,c=2$. The greedy algorithm will choose the solution set $\{b\}$ with value $3$. However, the best solution is $\{a,c\}$ with solution $4$. 

(b) Let $V=\{a,b,c,d\},E=\{\{a,b\},\{b,c\},\{c,d\}\}$. Give weights $a=2,b=1,c=2,d=4$. This algorithm will choose the solution set $\{b,d\}$ with value $5$. However, a better solution is $\{a,d\}$ with value $6$. 

(c) 

Step 1: let $\text{OPT }(i)$ be the independent subset of $\{v_{1},\ldots,v_{i}\}$ with the highest total weight. If $J\subseteq[i]$, let $\text{val}(J)=\sum_{j\in J}w_{j}$.

Step 2: Recurrence relation $$\text{OPT }(i)=\begin{cases}\text{OPT }(i-2)\cup\{i\} &\text{ if } \text{val}(\text{OPT }(i-2))+w_{i}>\text{val}(\text{OPT }(i-1))\\
\text{OPT }(i-1)&\text{ otherwise}\end{cases}$$

Step 3: Proof:


Step 4: Base Cases: There are two base cases. The first is an empty vertex set. Obviously, $\text{OPT }(\emptyset)=\emptyset$ and $\text{val}(\emptyset)=0$. The second is a singleton vertex set. Obviously, $\text{OPT }(\{v_{1}\})=\{v_{1}\}$ and $\text{val}(v_{1})=w_{1}$

Step 5: The goal is to compute $\text{OPT }(n)$

Step 6: 

$$\begin{align*}
&\textbf{Algorithm } \text{Heaviest Independent Set}\\
&\textbf{Input: } \text{Vertex Set }V=\{v_{1},\ldots,v_{n}\}\\
&\textbf{Output: } \text{OPT }n\\
&\text{Let }A \text{ be an array of length }n+1\\
&A[0]=\emptyset; A[1]=\{v_{1}\}\\
&\textbf{For } 1<i\le n \textbf{ do:}\\
&\quad V_{1}=A[i-2]\cup\{i\}\\
&\quad V_{2}=A[i-1]\\
&\quad \textbf{If } \text{val}(V_{1}>V_{2}) \textbf{ then:}\\
&\quad \quad A[i]=V_{1}\\
&\quad \textbf{Else:}\\
&\quad \quad A[i]=V_{2}\\
&\quad \textbf{end if}\\
&\textbf{end for}\\
&\textbf{return } A[n]\\
\end{align*}$$

>[!note] 3


