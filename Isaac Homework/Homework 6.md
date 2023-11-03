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


>[!note] 3