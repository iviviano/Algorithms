>[!note] 1



>[!note] 2



>[!note] 3


Idea: reduce from [[3D Matching Problem]]

Let $X,Y,Z$ be sets of size $n$. Let $T\subseteq X\times Y\times Z$.

Let $V=X\sqcup Y\sqcup Z$. 


Idea: reduce from [[Set Cover]]:

Let $X$ be a set. Let $X_{i}$ be a collection of subsets of $X$. We want to ask: is there a collection of $k$ $X_{i}$ that covers $X$. 

Make a vertex $i$ for each subset $X_{i}$. Add an edge $e_{ij}=\{i,j\}$ for all $i,j$. $w(e_{ij})=|X_{i}\cap X_{j}|$. 

Is there a collection of vertices 