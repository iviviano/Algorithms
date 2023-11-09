>[!note] 1

Step 1:

Let $\texttt{OPT}(i,j)$ be the number of paths length $j$ to vertex $i$ from $1$.
Let $N(i)=\{k:(k,i)\in E\}$.

Step 2:
$$\texttt{OPT}(i,j)=\sum_{k\in N(i)}\texttt{OPT}(k,j-1)$$

Step 3:


Step 4: 
Base cases: $\texttt{OPT}(1,0)=1$. For all $i\ne 1$, $\texttt{OPT}(i,0)=0$. 


Step 5: The goal is to find $$\sum_{i\in S}p(i)=\sum_{i\in S}\texttt{OPT}(i,\min\{j:\texttt{OPT}(i,j)>0\})$$


Step 6:
$$\begin{align*}
&\textbf{Algorithm } \text{Large Jest}\\
&\textbf{Input: } \text{Directed Graph }G=(V,E)\\
&\textbf{Output: } \sum_{i\in S}p(i)\\
&Compute\ N(i) for\ all\ i\\
&\text{Let }N \text{ be an array of sets of ints}\\
&\textbf{For } 1\le i\le n\textbf{ do:}\\
&\quad \text{Let }cur \text{ be a set of integers}\\
&\quad \textbf{For } e\in E \textbf{ do:}\\
&\quad \quad \textbf{If } e \text{ ends at }i \textbf{ then:}\\
&\quad \quad \quad \text{add }e \text{ to }cur\\
&\quad \quad \textbf{end if}\\
&\quad \textbf{end for}\\
&\quad N[i]=cur\\
&\textbf{end for}\\
&\text{Let }memo[n+1][n] \text{ be an array of ints}\\
&memo[1][0]=1\\
&\textbf{For } 1<i\le n \textbf{ do:}\\
&\quad memo[i][0]=0\\
&\textbf{end for}\\
&\textbf{For } 1\le j\le n-1\textbf{ do:}\\
&\quad \textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad \quad memo[i][j]=\sum\{memo[k][j-1]:k\in N[i]\}\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\textbf{return } \sum_{i\in S}memo[i][\min\{j:memo[i][j]>0\}]\\
\end{align*}$$

Step 7: 

Computing $N$ has runtime !!!!!!

Initializing $memo$ is constant. The base cases are $O(n)$, since the for loop runs about $n$ times. The nested for loops run about $n^{2}$ times. The sum is $O(n)$, since each vertex has at most $n$ neighbors, so there are at most $n$ arguments to the sum. 

The return statement is $O(n^{2})$. The sum has at most $n$ terms. 

>[!note] 2


