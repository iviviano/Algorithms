>[!note] 1

Step 1: Let $x_{i}$ be the number of truckloads sent to plant $i$. Clearly, $$\sum_{i=1}^{n}x_{i}=m$$The goal is to maximize $$\sum_{i=1}^{n}f_{i}(x_{i})$$

Let $\texttt{OPT}(i,j)$ be the maximum value of $\sum_{l=1}^{i}f_{i}(x_{i})$ such that $\sum_{l=1}^{i}x_{l}=j$ . 

Step 2:$$\texttt{OPT}(i,j)=\max\{\texttt{OPT}(i-1,j-k)+f_{i}(k):0\le l\le j\}$$

Step 3: Proof: if there are $i$ factories and $j$ trucks, we can send anywhere from $0$ to $j$ trucks to factory $i$. If we send $k$ trucks to factory $i$, factory $i$ contributes $f_{i}(k)$ tons of candy. The rest of the factories (1 through $i-1$) contribute at most $\texttt{OPT}(i-1,j-k)$ tons of chocolate. Therefore, the maximum amount of chocolate for $i$ factories and $j$ trucks is given by $$\texttt{OPT}(i,j)=\max\{\texttt{OPT}(i-1,j-k)+f_{i}(k):0\le l\le j\}$$
Step 4: Base cases:
For all $0\le i\le n$, $$\texttt{OPT}(i,0)=\sum_{j=1}^{i}f_{j}(0)$$since 0 truckloads may be sent to each factory if there are 0 truckloads total. Additionally, for all $0\le j\le m$, $$\texttt{OPT}(0,j)=0$$since no chocolate can be produced without any factories. 

Step 5: The goal is to find $\texttt{OPT}(n,m)$

Step 6: $$\begin{align*}
&\textbf{Algorithm } \text{Beans of Production}\\
&\textbf{Input: } \text{Parameters }m,n \text{ and functions }f_{i}\text{ for }1\le i\le n\\
&\textbf{Output: } \texttt{OPT}(n,m)\\
&\text{Let }A[n+1][m+1] \text{ be a two dimensional array} \\
&\textbf{For } 0\le j\le m \textbf{ do:}\\
&\quad A[0][j]=0\\
&\textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad A[i][0]=A[i-1][0]+f_{i}(0)\\
&\textbf{For } 1\le i\le n\textbf{ do:}\\
&\quad \textbf{For } 1\le j\le m \textbf{ do:}\\
&\quad \quad A[i][j]=\max\{A[i-1][j-k]:1\le k\le j\}\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\textbf{return } A[n][m]\\
\end{align*}$$
Step 7: 
Creating the array is $O(1)$. The first for loop is $O(m)$. The second for loop is $O(n)$. The nested for loops run a total of $mn$ times. The body of the nested loops is $O(m)$. Therefore, the algorithm is $O(m^{2}n)$.


>[!note] 2

Step 1:
Let $\texttt{OPT}(i,j)$ be the maximum value of a matchems game using the substring $s_{i},\ldots,s_{j}$. 

Step 2: Recurrence relations:
Let $$\texttt{OPT'}(i,j)=\max\{\texttt{OPT}(i+1,j)+p(s_{i}),\texttt{OPT}(i,j-1)+p(s_{j})\}$$Then, $$\texttt{OPT}(i,j)=\begin{cases}\texttt{OPT'}(i,j)\text{ if }s_{i}\ne s_{j} \\
\max\{\texttt{OPT'}(i,j),d(s_{i})+\texttt{OPT}(i+1,j+1\text{ if }s_{i}=s_{j}\end{cases}$$
Step 3: We can always remove the first letter or last letter of $s$. Removing the letter gives $p(s_{i})$ points. The rest of the string is then given by $s_{i+1},\ldots,s_{j}$. So, the best game that results from removing $s_{i}$ is given by $p(s_{i})+\texttt{OPT}(i+1,j)$. Similarly, the best game that results from removing $s_{j}$ is given by $p(s_{j})+\texttt{OPT}(i,j-1)$. If the first and last letters of the string match, we have the additional option of removing them both. This gives $d(s_{i})=d(s_{j})$ points, and leaves the string $s_{i+1},\ldots,s_{j-1}$. Therefore, the best game that results from removing both letters is $d(s_{i})+\texttt{OPT}(i+1,j-1)$. 

Step 4: 
Base cases: If $i=j$, then the string is a single character, so $$\texttt{OPT}(i,i)=p(s_{i})$$for all $i$. If $i>j$, then the string is empty, so $$\texttt{OPT}(i,j)=0$$
Step 5:
The goal is to find $\texttt{OPT}(1,n)$

Step 6: $$\begin{align*}
&\textbf{Algorithm } \text{Matchems}\\
&\textbf{Input: } \text{String }s_{1}\ldots,s_{n}\text{, functions }p \text{ and }d\\
&\textbf{Output: } \texttt{OPT}(1,n)\\
&\text{Let }memo[n+1][n+1]\text{ be an array of integers}\\
&\textbf{For } 0\le i\le n \textbf{ do:}\\
&\quad memo[i][i]=p(s_{i})\\
&\textbf{For } 1\le j\le n \textbf{ do:}\\
&\quad \textbf{For } j> i\ge 0 \textbf{ do:}\\
&\quad \quad one=\max\{memo[i+1][j]+p(s_i),memo[i][j-1]+p(s_j)\}\\
&\quad \quad \textbf{If } s_i=s_j \textbf{ then:}\\
&\quad \quad \quad memo[i][j]=\max\{memo[i-1][j-1]+d(s_{i}),one\}\\
&\quad \quad \textbf{Else:}\\
&\quad \quad \quad memo[i][j]=one\\
&\quad \quad \textbf{end if}\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\textbf{return } memo[0][n] 
\end{align*}$$
Step 7:
Creating the array is $O(1)$. Handling the base cases is $O(n)$, since this for loop iterates $n+1$ times and each step is constant. The nested for loops run $O(n^{2})$ times. At most 3 indexing operations occur for each iteration, so the nested loops are $O(n^{2})$. Therefore, this algorithm is $O(n^{2})$.

>[!note] 3

Step 1: Let $\texttt{OPT}(i,j)$ be the minimum sum of placement and access costs for putting $j$ papers in offices $i$ through $n$. 

Step 2: $$\texttt{OPT}(i,j)=\min\{\texttt{OPT}(i+1,j-1)+O_{i},\texttt{OPT}(i+1,j)+some\}$$

Step 3:
Suppose we distribute $j>1$ copies. If we put a paper in office $i$, then $j-1$ papers are available for offices $i+1$ to $n$. The minimum cost of putting $j-1$ copies in these offices is $\texttt{OPT}(i+1,j-1)$. The cost of putting a copy in office $i$ is $O_{i}$. As the total access cost is not changed by this, the minimum total cost is given by $\texttt{OPT}(i+1,j-1)+O_{i}$ in this case.

If we don't put a copy in office $i$, there are $j$ copies available for offices $i+1$ through $n$. The minimum cost of putting $j$ copies in these offices is $\texttt{OPT}(i+1,j)$. 

Step 4:

Step 5: The goal is to find $$\min\{\texttt{OPT}(n,j):1\le j\le n\}$$

Step 6:

Step 7: