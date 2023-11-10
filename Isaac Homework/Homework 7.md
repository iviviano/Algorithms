>[!note] 1

Step 1:

Let $\texttt{OPT}(i,j)$ be the number of paths length $j$ to vertex $i$ from $1$. Let $N(i)=\{k:(k,i)\in E\}$. I will refer to $N(i)$ as the neighbors of $i$.

Step 2:
$$\texttt{OPT}(i,j)=\sum_{k\in N(i)}\texttt{OPT}(k,j-1)$$

Step 3:
A path from $1$ to $i$ must come through one of the neighbors of $i$. A path from $1$ to $i$ of length $j$ is a path of length $j-1$ to a neighbor $k$ of $i$ joined with the edge from $k$ to $i$. $\texttt{OPT}(k,j-1)$ counts the number of paths length $j-1$ to $k$. So, the number of paths length $j$ to $i$ from $1$ that go through $k$ is $\texttt{OPT}(k,j-1)$. Therefore, $$\texttt{OPT}(i,j)\le\sum_{k\in N(i)}\texttt{OPT}(k,j-1)$$
Now, suppose $P,Q$ are two paths of length $j-1$ to different neighbors $p,q$ of $i$. Then, $P\cup\{(p,i)\}\ne Q\cup\{(q,i)\}$. Since any two paths to $i$ that come to $i$ through different neighbors of $i$ are distinct, $$\texttt{OPT}(i,j)\ge \sum_{k\in N(i)}\texttt{OPT}(k,j-1)$$

Step 4: 
Base cases: $\texttt{OPT}(1,0)=1$. For all $i\ne 1$, $\texttt{OPT}(i,0)=0$. 
$\texttt{OPT}(i,n)=0$. It is impossible to have a path as long as the number of vertices in the graph, since paths may not pass the same vertex twice. 

Step 5: The goal is to find $$\sum_{i\in S}p(i)=\sum_{i\in S}\texttt{OPT}(i,\min\{j:\texttt{OPT}(i,j)>0\})$$


Step 6:
$$\begin{align*}
&\textbf{Algorithm } \text{Large Jest}\\
&\textbf{Input: } \text{Directed Graph }G=(V,E)\\
&\textbf{Output: } \sum_{i\in S}p(i)\\
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
&\text{Let }memo[n+1][n+1] \text{ be an array of ints}\\
&memo[1][0]=1\\
&memo[1][n]=0\\
&\textbf{For } 1<i\le n \textbf{ do:}\\
&\quad memo[i][0]=0\\
&\quad memo[i][n]=0\\
&\textbf{end for}\\
&\textbf{For } 1\le j\le n-1\textbf{ do:}\\
&\quad \textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad \quad memo[i][j]=\sum\{memo[k][j-1]:k\in N[i]\}\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\textbf{return } \sum_{i\in S}memo[i][\min\{n,j:memo[i][j]>0\}]\\
\end{align*}$$

Step 7: 

Initializing $N$ is constant. The first for loop runs $n$ times. Its interior loop runs at most $O(n^{2})$ times, since graphs have $O(n^{2})$ edges. The body of these nested for loops is constant, since set addition is constant. Therefore, Computing $N$ is $O(n^{3})$.

Initializing $memo$ is constant. The base cases are $O(n)$, since the for loop runs about $n$ times. The second nested for loops run about $n^{2}$ times. The sum is $O(n)$, since each vertex has at most $n$ neighbors, so there are at most $n$ arguments to the sum. Therefore, computing $memo$ is $O(n^{3})$

The return statement is $O(n^{2})$. The sum has at most $n$ terms, and computing each term takes the minimum of at most $n+1$ things.

So, the algorithm is $O(n^{3})$.

>[!note] 2


Note: for any graph with a negative cycle, there will be a minimum path with length $-\infty$. Here is an example of a graph with a negative cycle for which [[Dijstra's Algorithm]] fails to return $-\infty$ for a path: 

Here is the table for the algorithm starting at $A$. 