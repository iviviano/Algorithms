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

Step 1: Let $\texttt{OPT}(i,j)$ be the minimum sum of placement and access costs for putting $j$ papers in offices $i$ through $n-1$. Let $o_{i}$ be the smallest index $o_{ij}\ge i$ such that a copy is put in $i$ for the solution that gives $\texttt{OPT}(i,j)$.

Step 2: $$\texttt{OPT}(i,j)=\min\{\texttt{OPT}(i+1,j-1)+O_{i},\texttt{OPT}(i+1,j)+o_{i+1,j}-i\}$$

Step 3:
Suppose $j>0$, so there is a copy in office $n$ and additional copies to distribute to the rest of the offices. If we put a paper in office $i$, then $j-1$ papers are available for offices $i+1$ to $n-1$. The minimum cost of putting $j-1$ copies in these offices is $\texttt{OPT}(i+1,j-1)$. The cost of putting a copy in office $i$ is $O_{i}$. As the total access cost is not changed by this, the minimum total cost is given by $\texttt{OPT}(i+1,j-1)+O_{i}$ in this case.

If we don't put a copy in office $i$, there are $j$ copies available for offices $i+1$ through $n-1$. The minimum cost of putting $j$ copies in these offices is $\texttt{OPT}(i+1,j)$. Since office $i$ does not have a copy, it has an access penalty. The access penalty is the smallest indexed office that contains a copy minus $i$. The optimal solution in this case has cost $\texttt{OPT}(i+1,j)$, so this smallest indexed office is $o_{i+1,j}$. So, the minimum total cost in this case is given by $\texttt{OPT}(i+1,j)+o_{i+1,j}-i$.

Step 4: Base Cases: 
If $j=0$, $o_{ij}=n$ for all $i$, since no copies are placed in any of the offices $i$ through $n-1$. $\texttt{OPT}(i,0)=O_{n}+\sum_{i=1}^{n-1}n-i$. The only office cost comes from office $n$. The total accessing penalty is $\sum_{i=1}^{n-1}n-i$.
If $j=n-i$, $o_{i,n-i}=i$, since there are enough copies to put one in every office from $i$ to $n-1$, and office $n$ always has a copy. In this case, there are no access costs, so $\texttt{OPT}(i,n-i)=\sum_{k=i}^{n}O_{k}$.

Step 5: The goal is to find $$\min\{\texttt{OPT}(n,j):1\le j\le n\}$$

Step 6:
$$\begin{align*}
&\textbf{Algorithm } \text{The Office Dilemma}\\
&\textbf{Input: } \text{Office weights }O_{i}\\
&\textbf{Output: } \text{The miminum total cost}\\
&\text{Let }memo[n+1][n+1]\text{ be an array of integers}\\
&\text{Let }o[n+1][n+1] \text{ be an array of integers}\\
&memo[n][0]=O_{i}\\
&\textbf{For } n> i\ge 1\textbf{ do:}\\
&\quad o[i][0]=n\\
&\quad memo[i][0]=memo[i+1][0]+n-i\\
&\textbf{For } 1\le i\le n \textbf{ do:}\\
&\quad o[i][n-i]=i\\
&\quad memo[i][n-i]=memo[i-1][n-(i-1)]+O_{i}\\
&\textbf{For } 0\le j\le n-1 \textbf{ do:}\\
&\quad \textbf{For } n-j>i\ge 1 \textbf{ do:}\\
&\quad \quad add=memo[i+1][j-1]+O_{i}\\
&\quad \quad not=memo[i+1][j]+o[i+1][j]-i\\
&\quad \quad \textbf{If } add>not \textbf{ then:}\\
&\quad \quad \quad o[i][j]=i\\
&\quad \quad \quad memo[i][j]=add\\
&\quad \quad \textbf{Else:}\\
&\quad \quad \quad o[i][j]=o[i+1][j]\\
&\quad \quad \quad memo[i][j]=not\\
&\quad \quad \textbf{end if}\\
&\quad \textbf{end for}\\
&\textbf{end for}\\
&\textbf{return } \min\{memo[n][j]:0\le j\le n-1\}
\end{align*}$$

Step 7:
The first and second for loops have runtime $O(n)$, since they iterate about $n$ times and have constant runtime bodies. The nested loops run about $n^{2}$ times. The body of the nested loops requires two indexing operations, so it is constant. So, the nested loops are $O(n^{2})$. The return statement is $O(n)$. Therefore, the algorithm is $O(n^{2})$.