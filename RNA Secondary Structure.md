RNA comprised of bases: U, G, C, A

Has a tendency to pair A with U and G with C

Idea: try to maximize pairings between in a string

Notation: 
- label bases in order
- list of pairings $(i,j),(k,l),...$

Rules:
- each base can only be matched once
- correct pairings of bases
- no sharp turns: $(i,j)$ is a valid pair only if $j>i+4$
- Non-crossing: $(i,j),(k,l)$ both pairs implies $i<k<j<k$ is false

Input: Sequence of $n$ bases
Output: Maximum number of pairs satisfying rules 1-4

Step 1: Let $\texttt{OPT}(i,j)$ be the max number of base pairs on $\{i,i+1,\ldots,j\}$.

Recurrence: $$\begin{split}\texttt{OPT}(i,j)=\max\{\texttt{OPT}(i,j-1)&,1+\texttt{OPT}(i,t-1)\\&+(\texttt{OPT}(t+1,j-1):t \text{ satisfies rules}\}\end{split}$$
$\texttt{OPT}(i,j-1)$ happens when we pair $j$. 

Step 4: Base cases: