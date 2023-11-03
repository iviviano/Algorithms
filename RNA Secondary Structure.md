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

