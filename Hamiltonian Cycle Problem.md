Input:
- A [[Directed Graph]] $G=(V,E)$

Output:
- Is there a [[Cycle]] that contains $V$

>[!def]
>A *hamiltonian cycle* is an ordering of vertices $v_{1},\ldots,v_{n}$ such that $(v_{i},v_{i+1})\in E$ for all $i<n$ and $(v_{n},v_{1})\in E$.

Show this is in $NP$:
- [[Certificate]]: an ordering of all of the vertices
- [[Certification]]: does the [[Certificate]] have the required $n$ [[edge]]s

Show this is in [[NP-Hard]]:
- reduce from [[3-SAT Problem]]

Step 1: Variable Assignments
- For each variable $x_{i}$, create a two way path $P_{i}$ of enough length
- To traverse all vertices, must go $L \rightarrow R$ ($x_{i}=\texttt{true}$) all the way or $R\rightarrow L$ ($x_{i}=\texttt{false}$) all the way.
- Create a start $s$ and end $t$
- Connect $s$ to both ends of $P_{1}$ for all $i$, connect both ends of $P_{i}$ to both ends of $P_{i+1}$
- Connect both ends of $P_{n}$ to $t$.
- Connect $t$ to $s$

Step 2: Satisfy Clauses
- For each clause, create special "clause vertex"
- 

